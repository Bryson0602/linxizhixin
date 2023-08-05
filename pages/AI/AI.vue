<template>
	<view class="chat">
		
		
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
					
					<uni-icons type="refreshempty" size="10" class="refresh" @click="exchange"></uni-icons>
					
					  <text class="huan" @click="exchange">换一换</text></br>
					  <!-- 需要替换的模块 -->
					  <view v-if="symbol==true">
						<text class="small" @click="send5">{{text5}}</text></br>
						<text class="small" @click="send6">{{text6}}</text></br>
						<text class="small" @click="send7">{{text7}}</text></br>
						<text class="small" @click="send8">{{text8}}</text>  
					  </view>
					  <view v-else>
						<text class="small" @click="send1">{{text1}}</text></br>
						<text class="small" @click="send2">{{text2}}</text></br>
						<text class="small" @click="send3">{{text3}}</text></br>
						<text class="small" @click="send4">{{text4}}</text>
					  </view>
					
					</view>
				</view>
			    </transition>
				
				<view>
					<view v-if="tuijie==1" class="juzhong">
						<view class="flex-row xuexi" @click="gotuijie1">
						<view class="img">
							<image src="../../static/tuijie1.jpg" mode=""></image>
						</view>
						<view class="flex-col wenzi" >
							<text class="zsxx">小犀推荐 | 学习更多</text>
							<text class="wt">不确定的生活，也要勇敢去爱</text>
						</view>	
						</view>
						
					</view>
					<view v-if="tuijie==2" class="juzhong">
						<view class="flex-row xuexi" @click="gotuijie2">
						<view class="img">
							<image src="../../static/tuijie2.jpg" mode=""></image>
						</view>
						<view class="flex-col wenzi">
							<text class="zsxx">小犀推荐~ | 学习更多</text>
							<text class="wt">降低考前精神内耗，区分这些疲惫</text>
						</view>	
						</view>
					</view>
					<view v-if="tuijie==3" class="juzhong">
						<view class="flex-row xuexi" @click="gotuijie3">
						<view class="img">
							<image src="../../static/tuijie3.png" mode=""></image>
						</view>
						<view class="flex-col wenzi">
							<text class="zsxx">小犀推荐~ | 学习更多</text>
							<text class="wt">转载｜《头脑特工队》电影赏析</text>
						</view>	
						</view>
					</view>
					<view v-if="tuijie==4" class="juzhong">
						<view class="flex-row xuexi"  @click="gotuijie4">
						<view class="img">
							<image src="../../static/tuijie4.jpg" mode=""></image>
						</view>
						<view class="flex-col wenzi">
							<text class="zsxx">小犀推荐~ | 学习更多</text>
							<text class="wt">和博物馆来一场心灵的约会~</text>
						</view>	
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
					<view class="flex">
						<view @click="change" class="send-btn1">猜你想问</view>
						<view @click="change1" class="send-btn2">天气小灵通</view>
					</view>
					
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
				<view @click="handleSend" class="send-btn">发送</view>
				
				
			</view>
			
		</view>
		
	</view>
</template>
<script>
	export default {
		data() {
			return {
				tuijie:0,
				symbol:true,
				flag:"",
				//键盘高度
				keyboardHeight:0,
				//底部消息发送高度
				bottomHeight: 0,
				text1:"1.如何自我缓解抑郁情绪？",
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
			tuijie1(){
				this.tuijie=1
			},
			tuijie2(){
				this.tuijie=2
			},
			tuijie3(){
				this.tuijie=3
			},
			tuijie4(){
				this.tuijie=4
			},
			exchange(){
				this.symbol=!this.symbol
			},
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
				setTimeout(()=>{
					this.tuijie1();
				},1000)
				
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
				this.tuijie2();
				
			
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
				this.tuijie3();
			},
			
			send8(){
				this.chatMsg2=this.text8
				console.log(this.text4)
				let obj = {
					botContent: "",
					recordId: 0,
					titleId: 0,
					userContent: this.chatMsg2,
					userId: 0,
					
				}
							
				this.msgList.push(obj);
				this.answer2();
				this.tuijie4();
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
			change1(){
				this.chatMsg2="今天天气怎么样~";
				let obj = {
					botContent: "",
					recordId: 0,
					titleId: 0,
					userContent: "今天天气怎么样~",
					userId: 0
				}
				this.msgList.push(obj);
				this.answer2();
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
			change(){
				this.flag="1";
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
		   gotuijie1(){
			   uni.navigateTo({
			   	url:"/pages/wzdetail/wzdetail?id=64bbda86652341bd64d48e59"
			   })
		   },
		   gotuijie2(){
		   			   uni.navigateTo({
		   			   	url:"/pages/wzdetail/wzdetail?id=64bbc0df2139291cebbb4c35"
		   			   })
		   },
		   gotuijie3(){
		   			   uni.navigateTo({
		   			   	url:"/pages/wzdetail/wzdetail?id=64bb7cb3337a9f4db7919615"
		   			   })
		   },
		   gotuijie4(){
		   			   uni.navigateTo({
		   			   	url:"/pages/wzdetail/wzdetail?id=64bdf32f7ad52ddc64db6f4e"
		   			   })
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
	.xuexi{
		margin-top: 20rpx;
		margin-bottom: 20rpx;
		margin-right: 20rpx;
		margin-left: 48rpx;
		background-color: #ffffff;
		border-radius: 24rpx;
		width: 660rpx;
		height: 150rpx;
		position: relative;
		.img{
			margin:15rpx 0 15rpx 15rpx ;
			background-color: #dbf3f7;
			width: 160rpx;
			height: 120rpx;
			border-radius: 24rpx;
			overflow: hidden;
			image{
			    width: 160rpx;
			    height: 120rpx;
			}
		}
		.wenzi{
			//margin-right: 30rpx;
			.zsxx{
				margin-left: 30rpx;
				margin-top: 30rpx;
				font-size: 20rpx;
				color: #8a8a8a;
			}
			.wt{
				margin-left: 30rpx;
				margin-top: 10rpx;
				font-size: 30rpx;
				font-weight: 700;
				color: #3f3f3f;
			}
		}
		.img1{
			right: 15rpx;
			top: 15rpx;
			position: absolute;
			//margin:15rpx 15rpx 0 15rpx ;
			background-color: #d0d0d0;
			width: 70rpx;
			height: 45rpx;
			border-radius: 15rpx;
			overflow: hidden;
			image{
				margin: auto auto;
			    width: 25rpx;
			    height: 25rpx;
			}
		}
	}
	.flex{
		display:flex;
	}
	.send-btn1 {
		display: flex;
		align-items: center;
		justify-content: center;
		padding-bottom: 7rpx;
		margin-bottom: 15rpx;
		margin-left: 25rpx;
		width: 150rpx;
		height: 78rpx;
		background: linear-gradient(to bottom right, #d9fffc, white);
		border-radius: 38rpx;
		font-size: 28rpx;
		font-family: PingFang SC;
		font-weight: 500;
		color: #767481;;
		line-height: 28rpx;
	}
	
	.send-btn2 {
		display: flex;
		align-items: center;
		justify-content: center;
		padding-bottom: 7rpx;
		margin-bottom: 15rpx;
		margin-left: 25rpx;
		width: 170rpx;
		height: 78rpx;
		background: linear-gradient(to bottom right, #e7ffd7, white);
		border-radius: 38rpx;
		font-size: 28rpx;
		font-family: PingFang SC;
		font-weight: 500;
		color: #767481;;
		line-height: 28rpx;
	}
	
	.fade-enter-active, .fade-leave-active {
	  transition: opacity .5s;
	}
	
	.fade-enter, .fade-leave-to {
	  opacity: 0;
	}
	.juzhong{
		text-align: center;
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
		color:#7bc2f0///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
	}
	
	.text1{
		margin-top: 15rpx;
		padding-top: 25rpx;
		padding-left: 25rpx;
		color:#eba76f
	}
	.guess{
		margin-bottom: 20rpx;
		position: flex;
		border-radius: 25rpx;
		margin-left:7%;
		width:85%;
		height:250rpx;
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
			background-color: #F2F2F2;//需改
			
			.chat-body {
				border-top: none;
				display: flex;
				flex-direction: column;
				
				background-color:#F2F2F2;
				height:100%;
				.self {
					justify-content: flex-end;
				}
				.item {
					display: flex;
					padding: 23rpx 30rpx;
					// background-color: greenyellow;

					.right {
						background: linear-gradient(to bottom right, #ffefe7, white);

                            //#ffefda #d5e7ff
					}
					.left {
						// background: linear-gradient(to bottom right, #d9fffc, white);
						background: linear-gradient(
									    to bottom right, 
									    #eafbff 0%,
									    #edfbff 20%,
									    #edfbfe 40%,
									    #e8f8fe 60%,
									    #eaf1fb 80%,
									    #e8e6fb 100%
									  );
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
						border-right: 12rpx solid #edfbff;
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
						color: #767481;
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
				padding-bottom: 7rpx;
                
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
				padding-bottom: 7rpx;
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

