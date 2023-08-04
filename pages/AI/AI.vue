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
						<b><text style="color: #616161;">猜你想问</text></b> </br>
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
				
				<transition name="fade">
				<view class="guess1" v-if="flag!=''">
					<view class="text1">
					<b><text style="color: #616161;">猜你想问</text></b> 
					
					<uni-icons type="refreshempty" size="10" class="refresh"></uni-icons>
					  <text class="huan">换一换</text></br>
					  <view>
						<text class="small" @click="send5">{{text5}}</text></br>
						<text class="small" @click="send6">{{text6}}</text></br>
						<text class="small" @click="send7">{{text7}}</text></br>
						<text class="small" @click="send8">{{text8}}</text>  
					  </view>
					
					</view>
				</view>
			    </transition>
					
				
				
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
						auto-height placeholder="请输入你的问题~" placeholder-style="color: #C0C0C0"></textarea>
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
				flag:"",
				//键盘高度
				keyboardHeight:0,
				//底部消息发送高度
				bottomHeight: 0,
				text1:"1.如何自我缓解抑郁情绪",
				text2:"2.面对负面情绪时该选择什么样的方式释放？",
				text3:"3.怎么结束“自我内耗”？",
				text4:"4.心理保健自修室",
				text5:"1.如何应对失恋和分手的伤痛？",
				text6:"2.如何处理学习与生活的平衡问题？",
				text7:"3.如何有效地沟通和解决冲突？",
				text8:"4.如何应对社交焦虑和害羞？",
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
				msgList2:[
					
				]	,
				msgList:[
					
				]	,
				msgList3:[
					
				]
			}
		},
		updated(){
					//页面更新时调用聊天消息定位到最底部
					this.scrollToBottom();
				},
		computed:{
			windowHeight() {
			    return this.rpxTopx(uni.getSystemInfoSync().windowHeight)
			},
			// 键盘弹起来的高度+发送框高度
			inputHeight(){
				return this.bottomHeight+this.keyboardHeight
			}
		},
		onLoad(){
					uni.onKeyboardHeightChange(res => {
						//这里正常来讲代码直接写
						//this.keyboardHeight=this.rpxTopx(res.height)就行了
						//但是之前界面ui设计聊天框的高度有点高,为了不让键盘和聊天输入框之间距离差太大所以我改动了一下。
						this.keyboardHeight = this.rpxTopx(res.height-30)
						if(this.keyboardHeight<0)this.keyboardHeight = 0;
					})
				},
				onUnload(){
					uni.offKeyboardHeightChange()
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
			send5(){
				this.chatMsg2=this.text5
				console.log(this.text1)
				let obj = {
					botContent: "",
					recordId: 0,
					titleId: 0,
					userContent: this.chatMsg2,
					userId: 0
				}
							
				this.msgList.push(obj);
				
				this.answer2();
			},
			send6(){
				this.chatMsg2=this.text6
				console.log(this.text2)
				let obj = {
					botContent: "",
					recordId: 0,
					titleId: 0,
					userContent: this.chatMsg2,
					userId: 0
				}
							
				this.msgList.push(obj);
				this.answer2();
			
			},
			send7(){
				this.chatMsg2=this.text7
				console.log(this.text3)
				let obj = {
					botContent: "",
					recordId: 0,
					titleId: 0,
					userContent: this.chatMsg2,
					userId: 0
				}
							
				this.msgList.push(obj);
				this.answer2();
			},
			send8(){
				this.chatMsg2=this.text8
				console.log(this.text4)
				let obj = {
					botContent: "",
					recordId: 0,
					titleId: 0,
					userContent: this.chatMsg2,
					userId: 0
				}
							
				this.msgList.push(obj);
				this.answer2();
			},
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
			sendHeight(){
							setTimeout(()=>{
								let query = uni.createSelectorQuery();
								query.select('.send-msg').boundingClientRect()
								query.exec(res =>{
									this.bottomHeight = this.rpxTopx(res[0].height)
								})
							},10)
						},
		
			scrollToBottom(){
			   				 //外层加一个延时函数是为了能获取到节点的准确信息
							setTimeout(()=>{
								let query = uni.createSelectorQuery().in(this);
			       				 //获取节点信息
								query.select('#scrollview').boundingClientRect();
								query.select('#msglistview').boundingClientRect();
								query.exec((res) =>{
								if(res[1].height > res[0].height){
									this.scrollTop = this.rpxTopx(res[1].height - res[0].height)
								}
							})
						},150)
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
					this.flag="";
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
						this.flag="1";
					}			 
			   })
		   },
		   answer2(){
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
		   										this.flag="";
		   			   				}
		   							 
		   			   })
		   			  
		   			   
		   },
		  
		   
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
	.fade-enter-active, .fade-leave-active {
	  transition: opacity .5s;
	}
	
	.fade-enter, .fade-leave-to {
	  opacity: 0;
	}
		
	.huan{
		width:35rpx;
		font-size: 20rpx;
		margin-left: 5rpx;
		color: grey;
	}
	.text{
		margin-top: 15rpx;
		padding-top: 25rpx;
		padding-left: 25rpx;
		color:#4fd0f0
	}
	.text1{
		margin-top: 15rpx;
		padding-top: 25rpx;
		padding-left: 25rpx;
		color:#eba76f
	}
	.guess{
		position: flex;
		border-radius: 25rpx;
		margin-left:7%;
		width:85%;
		height:280rpx;
		background-image: radial-gradient(37.8% 37.8% at 77.9% 3.6%, #d5e7ff 0%, #ffffff 100%);
		box-shadow: black;
	}
	.guess1{
		position: flex;
		border-radius: 25rpx;
		margin-left:7%;
		width:85%;
		height:280rpx;
		background-image: radial-gradient(56% 56% at 41.4% 4.2%, #ffefda 0%, #ffffff 100%);
		box-shadow: black;
	}
    .small{
		font-size: 31rpx;
		//text-decoration:underline;
		
		padding-bottom: 2rpx;
	}
    .refresh{
	margin-left: 350rpx;
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
				background-color:#F2F2F2;
				
				.self {
					justify-content: flex-end;
				}
				.item {
					display: flex;
					padding: 23rpx 30rpx;
					// background-color: greenyellow;

					.right {
						background: linear-gradient(to bottom right, #d9fffc, white);

                            //#ffefda #d5e7ff
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
						border-left: 12rpx solid white;
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
						border-radius: 28rpx;
						word-wrap: break-word;
						padding: 24rpx 24rpx;
						margin: 0 24rpx;
						border-radius: 15px;
						font-size: 32rpx;
						font-family: PingFang SC;
						font-weight: 500;
						color: #616161;
						line-height: 42rpx;
					}

					.avatar {
						display: flex;
						justify-content: center;
						width: 78rpx;
						height: 78rpx;
						background: #ccd0c2;
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
					min-height: 65rpx;
					max-height: 500rpx;
					background: #FFFFFF;
					border-radius: 48rpx;
					font-size: 32rpx;
					font-family: PingFang SC;
					color: #333333;
					line-height: 72rpx;
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
				height: 78rpx;
				background: #3adbdd;
				border-radius: 38rpx;
				font-size: 28rpx;
				font-family: PingFang SC;
				font-weight: 500;
				color: white;
				line-height: 28rpx;
			}
		}
		
	}
</style>
