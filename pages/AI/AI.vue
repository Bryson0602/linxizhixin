<template>
	<view class="chat">
		<view class="status_bar">
		    <!-- 这里是状态栏 -->
		</view>
		<scroll-view  :style="{height: `${windowHeight}rpx`}"
		id="scrollview"
		scroll-y="true" 
		:scroll-top="scrollTop"
		:scroll-with-animation="true"
		class="scroll-view"
		>
			<!-- 聊天主体 -->
			<view id="msglistview" class="chat-body">
				<view v-for="(item,index1) in msgList1" :key="index1">
					
					<!-- 机器人发的消息 -->
					<view class="item Ai" v-if="item.botContent != ''">
						<!-- 头像 -->     
						<view class="avatar">
						</view>
						<!-- 文字内容 -->
						<view class="content left">
							{{item.botContent}}
						</view>
					</view>
					<view class="guess">
						<view class="text">
						<text>猜你想问</text></br>
						<text class="small" @click="send1">{{text1}}</text></br>
						<text class="small" @click="send2">{{text2}}</text></br>
						<text class="small" @click="send3">{{text3}}</text></br>
						<text class="small" @click="send4">{{text4}}</text>
						</view>
					</view>
				</view>
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
						</view>
					</view>
					<!-- 机器人发的消息 -->
					<view class="item Ai" v-if="item.botContent != ''">
						<!-- 头像 -->     
						<view class="avatar">
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
		<view class="chat-bottom">
			<view class="send-msg">
                <view class="uni-textarea">
					
					<textarea v-model="chatMsg"
					  maxlength="300"
					  :show-confirm-bar="false"
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
				text1:"1.如何自我缓解抑郁情绪",
				text2:"2.面对负面情绪时该选择什么样的方式释放？",
				text3:"3.怎么结束“自我内耗”？",
				text4:"4.心理保健自修室",
				//滚动距离
				scrollTop: 0,
				userId:'',
				//发送的消息
				chatMsg:"",
				chatMsg1:"",
				chatMsg2:"",
				chatMsg3:"",
				msgList1:[
					{
					    botContent: "你好，我是智能心理助手小犀~有什么可以帮助你的呢？",
					    recordId: 0,
					    titleId: 0,
					    userContent: "",
					    userId: 0
					},
					
					
				]	,
				msgList:[
					
				]	
			}
		},
		computed: {
			windowHeight() {
				
			    return this.rpxTopx(uni.getSystemInfoSync().windowHeight)
			}
		},
		methods:
		{
			send1(){
				this.chatMsg2=this.text1
				console.log(this.text1)
				let obj = {
					botContent: "",
					recordId: 0,
					titleId: 0,
					userContent: this.chatMsg2,
					userId: 0
				}
							
				this.msgList.push(obj);
				this.answer1();
			},
			send2(){
				this.chatMsg2=this.text2
				console.log(this.text2)
				let obj = {
					botContent: "",
					recordId: 0,
					titleId: 0,
					userContent: this.chatMsg2,
					userId: 0
				}
							
				this.msgList.push(obj);
				this.answer1();
			},
			send3(){
				this.chatMsg2=this.text3
				console.log(this.text3)
				let obj = {
					botContent: "",
					recordId: 0,
					titleId: 0,
					userContent: this.chatMsg2,
					userId: 0
				}
							
				this.msgList.push(obj);
				this.answer1();
			},
			send4(){
				this.chatMsg2=this.text4
				console.log(this.text4)
				let obj = {
					botContent: "",
					recordId: 0,
					titleId: 0,
					userContent: this.chatMsg2,
					userId: 0
				}
							
				this.msgList.push(obj);
				this.answer1();
			},
			// px转换成rpx
			rpxTopx(px){
				let deviceWidth = wx.getSystemInfoSync().windowWidth
				let rpx = ( 750 / deviceWidth ) * Number(px)
				return Math.floor(rpx)
			},
			// 发送消息
			handleSend() {
				//如果消息不为空
				if(!this.chatMsg||!/^\s+$/.test(this.chatMsg)){
					let obj = {
						botContent: "",
						recordId: 0,
						titleId: 0,
						userContent: this.chatMsg,
						userId: 0
					}
					this.msgList.push(obj);
					this.answer();
					this.chatMsg = "";
				}else {
					this.$modal.showToast('不能发送空白消息')
				}
			},
           answer(){
			   uni.request({
			   	url:"https://api.ownthink.com/bot?appid=386a5bb9d5eb623023988f0e52cd4df3&userid=user&spoken="+this.chatMsg,
			   				success:res=>{
								console.log(res.data.data.info.text);
								this.chatMsg1=res.data.data.info.text
								let obj = {
									botContent: this.chatMsg1,
									recordId: 0,
									titleId: 0,
									userContent: "",
									userId: 0
								}
											
								this.msgList.push(obj);
			   				}
							 
			   })
			  console.log(this.chatMsg)
			   
			   
		   },
		   answer1(){
		   			   uni.request({
		   			   	url:"https://api.ownthink.com/bot?appid=386a5bb9d5eb623023988f0e52cd4df3&userid=user&spoken="+this.chatMsg2,
		   			   				success:res=>{
		   								console.log(res.data.data.info.text);
		   								this.chatMsg3=res.data.data.info.text
		   								let obj = {
		   									botContent: this.chatMsg3,
		   									recordId: 0,
		   									titleId: 0,
		   									userContent: "",
		   									userId: 0
		   								}
		   											
		   								this.msgList.push(obj);
		   			   				}
		   							 
		   			   })
		   			  
		   			   
		   }
		}
	}
</script>
<style lang="scss" scoped>
	
	$chatContentbgc: #C2DCFF;
	$sendBtnbgc: #4F7DF5;
	
	view,button,text,input,textarea {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}
	.text{
		margin-top: 15rpx;
		padding-top: 25rpx;
		padding-left: 25rpx;
	}
	.guess{
		position: flex;
		border-radius: 25rpx;
		margin-left:7%;
		width:85%;
		height:280rpx;
		background-color:navajowhite;
		box-shadow: black;
	}
    .small{
		font-size: 31rpx;
		//text-decoration:underline;
		border-bottom: 1rpx solid darkgrey;
		padding-bottom: 5rpx;
	}

	/* 聊天消息 */
	.chat {
		position: flex;
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
						width: 78rpx;
						height: 78rpx;
						background: $sendBtnbgc;
						border-radius: 8rpx;
						overflow: hidden;
						
						image {
							align-self: center;
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

			.send-msg {
				display: flex;
				align-items: flex-end;
				padding: 16rpx 30rpx;
				width: 100%;
				min-height: 177rpx;
				position: fixed;
				bottom: 0;
				background: #EDEDED;
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
				justify-content: center;
				margin-bottom: 70rpx;
				margin-left: 25rpx;
				width: 128rpx;
				height: 75rpx;
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
