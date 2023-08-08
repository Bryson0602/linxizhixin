<template>
	<view class="chat">
		<scroll-view  :style="{height: `${windowHeight-inputHeight}rpx`}"
		id="scrollview"
		scroll-y="true" 
		:scroll-top="scrollTop"
		class="scroll-view"
		>
			<!-- 聊天主体 -->
			<view id="msglistview" class="chat-body">
				<!-- 聊天记录 -->
				<view v-for="(item,index) in msgList" :key="index">
					<!-- 自己发的消息 -->
					<view class="item self" v-if="item.userContent != ''" >
						<!-- 文字内容 -->
						<view class="content right">
							{{item.userContent}}
						</view>
						<!-- 头像 -->
						<view class="avatar">
							<image src="../../static/lxzx.png" mode=""></image>
						</view>
					</view>
					<!-- 机器人发的消息 -->
					<view class="item Ai" v-if="item.botContent != ''">
						<!-- 头像 -->     
						<view class="avatar">
							<image :src="url" mode=""></image>
						</view>
						<!-- 文字内容 -->
						<view class="content left">
							{{item.botContent}}
						</view>
					</view>
				</view>
			</view>
		</scroll-view>
		
		<!-- 底部消息发送栏 -->
		<!-- 用来占位，防止聊天消息被发送框遮挡 -->
		<view class="chat-bottom" :style="{height: `${inputHeight}rpx`}">
			<view class="send-msg" :style="{bottom:`${keyboardHeight}rpx`}">
                <view class="uni-textarea">
					<textarea v-model="chatMsg"
					  maxlength="300"
					  confirm-type="send"
					  @confirm="handleSend"
					  :show-confirm-bar="false"
					  :adjust-position="false"
					  @linechange="sendHeight"
					  @focus="focus" @blur="blur"
					 auto-height></textarea>
				</view>
				<button @click="handleSend" class="send-btn">发送</button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				name:'',
				url:"",
				id:100,
				//键盘高度
				keyboardHeight:0,
				//底部消息发送高度
				bottomHeight: 0,
				//滚动距离
				scrollTop: 0,
				userId:'',
				//发送的消息
				chatMsg:"",
				msgList:[
					{
					    botContent: "我们已经是好友了，现在可以开始聊天啦~",//机器人
					    recordId: 0,
					    titleId: 0,
					    userContent: "",
					    userId: 0
					},
					// {
					//     botContent: "",
					//     recordId: 0,
					//     titleId: 0,
					//     userContent: "你好呀",//自己
					//     userId: 0
					// }
				]	
			}
		},
		updated(){
			//页面更新时调用聊天消息定位到最底部
			this.scrollToBottom();
		},
		computed: {
			windowHeight() {
			    return this.rpxTopx(uni.getSystemInfoSync().windowHeight)
			},
			// 键盘弹起来的高度+发送框高度
			inputHeight(){
				return this.bottomHeight+this.keyboardHeight
			}
		},
		onLoad(option){
			//接受信息
			const name = option.name;
			const url = option.url;
			const id = option.id;
			this.name = name;
			this.url = url;
			this.id = id;
			uni.setNavigationBarTitle({
				title:this.name
			})
			// 从本地缓存中读取聊天记录（缓存）---------------------------------------
			  const chatMsgList = uni.getStorageSync('chatMsgList');
			  if (chatMsgList && chatMsgList.length > 0) {
			    this.msgList = chatMsgList;
			  }
			uni.onKeyboardHeightChange(res => {
				//这里正常来讲代码直接写
				//this.keyboardHeight=this.rpxTopx(res.height)就行了
				//但是之前界面ui设计聊天框的高度有点高,为了不让键盘和聊天输入框之间距离差太大所以我改动了一下。
				this.keyboardHeight = this.rpxTopx(res.height-30)
				if(this.keyboardHeight<0)this.keyboardHeight = 0;
			})
			
			if(this.id<=4)//固定的部分前台显示
			{
				this.msgList = [
					{
					    botContent: "",
					    recordId: 0,
					    titleId: 0,
					    userContent: "明天一起参加活动怎么样？",//自己
					    userId: 0
					},
					{
					    botContent: "好啊，地址在哪呀？",//机器人
					    recordId: 0,
					    titleId: 0,
					    userContent: "",
					    userId: 0
					},
					{
					    botContent: "",
					    recordId: 0,
					    titleId: 0,
					    userContent: "我到时候发你哦",//自己
					    userId: 0
					},
					{
					    botContent: "OK",//机器人
					    recordId: 0,
					    titleId: 0,
					    userContent: "",
					    userId: 0
					},
				];
			}
		},
		onUnload(){
			uni.offKeyboardHeightChange()
		},
		
		methods: {
			focus(){
				this.scrollToBottom()
			},
			blur(){
				this.scrollToBottom()
			},
			// px转换成rpx
			rpxTopx(px){
				let deviceWidth = wx.getSystemInfoSync().windowWidth
				let rpx = ( 750 / deviceWidth ) * Number(px)
				return Math.floor(rpx)
			},
			// 监视聊天发送栏高度
			sendHeight(){
				setTimeout(()=>{
					let query = uni.createSelectorQuery();
					query.select('.send-msg').boundingClientRect()
					query.exec(res =>{
						this.bottomHeight = this.rpxTopx(res[0].height)
					})
				},10)
			},
			// 滚动至聊天底部
			scrollToBottom(e){
				setTimeout(()=>{
					let query = uni.createSelectorQuery().in(this);
					query.select('#scrollview').boundingClientRect();
					query.select('#msglistview').boundingClientRect();
					query.exec((res) =>{
						if(res[1].height > res[0].height){
							this.scrollTop = this.rpxTopx(res[1].height - res[0].height)
						}
					})
				},15)
			},
			handleSend() {
			  if (!this.chatMsg || /^\s+$/.test(this.chatMsg)) {
			    this.$modal.showToast('不能发送空白消息')
			    return
			  }
			  const userMsg = this.chatMsg.trim(); // 去除消息前后的空格
			  
			  // 添加延时回复的逻辑
			  const obj = {
			    botContent: "",
			    recordId: 0,
			    titleId: 0,
			    userContent: userMsg,
			    userId: 0
			  };
			  this.msgList.push(obj);
			  this.chatMsg = '';
			  this.scrollToBottom();
			  // 将聊天记录存储到本地缓存中
			  uni.setStorageSync('chatMsgList', this.msgList);//-----------------
			  setTimeout(() => {
			    let botMsg = ""; // 机器人回复的消息
			    if (userMsg === "你好呀") {
			      botMsg = "Hello，你好~";
			    } else if (userMsg === "我跟你说一件事") {
			      botMsg = "咋啦？";
			    } else if (userMsg === "我最近学习压力好大，真的不知道该怎么办了") {
			      botMsg = "我在这呢，学习压力确实很大，但你要知道你不是一个人在战斗。我们都经历过类似的情况，所以我相信你有足够的力量来应对的。";
			    } else if (userMsg === "感觉学习真的好累啊") {
			      botMsg = "不要过分压力自己啦。学习是一个长期的过程，每个人都会有起伏和困难的。";
			    } else if (userMsg === "我们一起出去玩吧") {
			      botMsg = "OK！到时候你把地址发我哦~";
			    } 
				else {
			      botMsg = "你好呀~";
			    }
			    obj.botContent = botMsg; // 更新机器人回复的消息
			    this.scrollToBottom();
				uni.setStorageSync('chatMsgList', this.msgList);//-----------------
			  }, 2000); // 设置延时为2秒
			}

			// 发送消息
			// handleSend() {
			// 	//如果消息不为空
			// 	if(!this.chatMsg||!/^\s+$/.test(this.chatMsg)){
			// 		let obj = {
			// 			botContent: "",
			// 			recordId: 0,
			// 			titleId: 0,
			// 			userContent: this.chatMsg,
			// 			userId: 0
			// 		}
			// 		this.msgList.push(obj);
			// 		this.chatMsg = '';
			// 		this.scrollToBottom()
			// 	}else {
			// 		this.$modal.showToast('不能发送空白消息')
			// 	}
			// },
		}
	}
</script>

<style lang="scss" scoped>
	
	$chatContentbgc: #ffd2b7;
	$sendBtnbgc: #4F7DF5;
	
	view,button,text,input,textarea {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}

	/* 聊天消息 */
	.chat {
		//position: fixed;
		.scroll-view {
			::-webkit-scrollbar {
					    display: none;
					    width: 0 !important;
					    height: 0 !important;
					    -webkit-appearance: none;
					    background: transparent;
					    color: transparent;
					  }
			
			// background-color: orange;
			background-color: #F6F6F6;
			
			.chat-body {
				display: flex;
				flex-direction: column;
				padding-top: 23rpx;
				// background-color:skyblue;
				
				.self {
					justify-content: flex-end;
				}
				.item {
					display: flex;
					padding: 23rpx 30rpx;
					// background-color: greenyellow;

					.right {
						background-color: $chatContentbgc;
					}
					.left {
						background-color: #FFFFFF;
					}
                    // 聊天消息的三角形
					.right::after {
						position: absolute;
						display: inline-block;
						content: '';
						width: 0;
						height: 0;
						left: 100%;
						top: 10px;
						border: 12rpx solid transparent;
						border-left: 12rpx solid $chatContentbgc;
					}

					.left::after {
						position: absolute;
						display: inline-block;
						content: '';
						width: 0;
						height: 0;
						top: 10px;
						right: 100%;
						border: 12rpx solid transparent;
						border-right: 12rpx solid #FFFFFF;
					}

					.content {
						position: relative;
						max-width: 486rpx;
						border-radius: 8rpx;
						word-wrap: break-word;
						padding: 24rpx 24rpx;
						margin: 0 24rpx;
						border-radius: 5px;
						font-size: 32rpx;
						font-family: PingFang SC;
						font-weight: 500;
						color: #333333;
						line-height: 42rpx;
					}

					.avatar {
						display: flex;
						justify-content: center;
						width: 80rpx;
						height: 80rpx;
						
						background: $sendBtnbgc;
						border-radius: 8rpx;
						border-radius: 50%;
						overflow: hidden;
						
						image {
							align-self: center;
							width: 80rpx;
							height: 80rpx;
						}

					}
				}
			}
		}

		/* 底部聊天发送栏 */
		.chat-bottom {
			width: 100%;
			height: 177rpx;
			background: #F4F5F7;
			transition: all 0.1s ease;
			

			.send-msg {
				display: flex;
				align-items: flex-end;
				padding: 16rpx 30rpx;
				width: 100%;
				min-height: 177rpx;
				position: fixed;
				bottom: 0;
				background: #EDEDED;
				transition: all 0.1s ease;
			}

			.uni-textarea {
				padding-bottom: 70rpx;
                
				textarea {
					width: 537rpx;
					min-height: 75rpx;
					max-height: 500rpx;
					background: #FFFFFF;
					border-radius: 8rpx;
					font-size: 32rpx;
					font-family: PingFang SC;
					color: #333333;
					line-height: 43rpx;
					padding: 5rpx 8rpx;
				}
			}
            
			.send-btn {
				display: flex;
				align-items: center;
				//text-align: center;
				justify-content: center;
				margin-bottom: 70rpx;
				margin-left: 25rpx;
				width: 128rpx;
				height: 82rpx;//75
				background: $sendBtnbgc;
				border-radius: 8rpx;
				font-size: 28rpx;
				font-family: PingFang SC;
				font-weight: 500;
				color: #FFFFFF;
				line-height: 28rpx;
			}
		}
	}
</style>
