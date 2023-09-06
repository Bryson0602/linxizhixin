<template>
  <view class="flex-col page">
	  <view class="status_bar">
	      <!-- 这里是状态栏 -->
	  </view>
    <view class="flex-col flex-auto group">
      <view class="flex-col section space-y-13">
		  
        <view class="flex-row justify-center items-center group_2">
			<image @click="goTXLadd" class="image1" src="../../static/plus.png" mode=""></image>
          <view class="flex-col justify-start items-start relative text-wrapper">
            <text class="text">搜索你的好友</text>
          </view>
          <image
		    @click="gotxl"
            class="image"
            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16908596901104497480.png"
          />
          <image
		    @click="goTXLadd"
            class="image_2"
            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385894443945464.png"
          />
        </view>
		
        <view class="flex-row space-x-14">
          <view class="flex-col justify-start items-center equal-division-item" @click="gopipei" >
            <text class="font_1">智能匹配</text>
          </view>
          <view class="flex-col justify-start items-center relative equal-division-item bj" @click="popupClick">
            <image
              class="image_3 pos"
			  
              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385893796236975.png"
            />
			
			
			<view class="dingwei">

				<image
				  class="image_4 weizhi"
				  
				  :src="selectedEmoji.url"
				/>
				
				<text class="relative font_2">{{ selectedEmoji.name }}</text>
			</view>
            
			<!-- <image
			  class="self-center tupian"
			  :src="selectedEmoji"
			/> -->
          </view>
        </view>
      </view>
	  
	  
	  
	  
      <view class="flex-col relative section_2 space-y-11">
        <text class="self-start text_2">消息</text>
		
        <view class="flex-row items-center space-x-14" @click="gochat(item)" v-for="(item, index) in arrList" :key="id">
          <view class="section_3">
			  <image :src="item.url" mode=""></image>
		  </view>
          <view class="flex-col items-start space-y-8">
            <text class="font_2">{{item.name}}</text>
            <text class="font_3">{{item.msg}}</text>
          </view>
        </view>
		 <!-- <view class="flex-row items-center space-x-14">
		   <view class="section_3"></view>
		   <view class="flex-col items-start space-y-8">
		     <text class="font_2">咖啡不苦命苦</text>
		     <text class="font_3">真的假的啊哈哈哈</text>
		   </view>
		 </view>-->

      </view>
	  
	  <view class="content">
	  
	      <!-- <view class="popUpBtn" @click="popupClick">
	          点击显示弹框</view> -->
	  
	      <!-- 使用组件 isShow：设置弹框是否显示 width：宽度 height：高度 radius：圆角 -->
	      <cc-popup :isShow='isshow' width="0rpx" height="700rpx" radius="26rpx">
	  		<!-- calc(100vw - 70px) -->
	          <!-- 自定义展示内容 -->
	          <view class="modelContent">
	              <!-- <view style="margin-top: 6px;">
	  
	                  弹框标题
	              </view> -->
	  
	              <!-- <view style="margin-top: 20px; color: #666666; margin: 6px 12px;">
	  
	                  这是弹框内容 这是弹框内容 这是弹框内容 这是弹框内容
	              </view> -->
	  			<view class="flex-col pig">
	  			  <view class="flex-col flex-auto grass">
	  			    <view class="flex-col section space-y-13">
	  			      
	  			      <view class="flex-row space-x-14">
	  			        
	  					  <!-- </br> </br> </br></br></br></br></br> -->
	  			      </view>
	  			    </view>
	  			    <view class="flex-col justify-start relative group_3">
	  			      <view class="flex-col section_3 space-y-10">
	  
	  			      </view>
	  					
	  			      <view class="flex-col section_2 space-y-84 pos_2">
	  			        
	  					  <view class="flex-row justify-between container">
	  					    <view class="flex-row items-center equal-division-item_2 space-x-6 image-container" v-for="(emoji, index) in emojiList" :key="index">
	  					      <image
	  					        class="shrink-0 image8"

								:src="emoji.url"
								@click="selectEmoji(emoji)"
	  					      />
	  					      <text class="font_2" @click="selectEmoji(emoji)">{{emoji.name}}</text>
	  					    </view>
	  					    <!-- <view class="flex-row items-center equal-division-item_2 space-x-6">
	  					      <image
	  					        class="shrink-0 image_5"
	  					        src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16914818924027035923.png"
	  					      />
	  					      <text class="font_2">摸鱼中</text>
	  					    </view> -->
	  					  </view>
	  					  
	  			        <!-- <view class="flex-row justify-between">
	  			          <view class="flex-row items-center equal-division-item_2 space-x-6">
	  			            <image
	  			              class="shrink-0 image_5"
	  			              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16914818924048861981.png"
	  			            />
	  			            <text class="font_2">约咖啡</text>
	  			          </view>
	  			          <view class="flex-row items-center equal-division-item_2 space-x-6">
	  			            <image
	  			              class="shrink-0 image_5"
	  			              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16914818924054722157.png"
	  			            />
	  			            <text class="font_2">想回家</text>
	  			          </view>
	  			        </view> -->
	  			        <!-- <view class="flex-row justify-between equal-division">
	  			          <view class="flex-row equal-division-item_2 space-x-4">
	  			            <image
	  			              class="shrink-0 image_6"
	  			              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16914818924061154530.png"
	  			            />
	  			            <text class="self-center font_2">心情好</text>
	  			          </view>
	  			          <view class="flex-row equal-division-item_2 space-x-4">
	  			            <image
	  			              class="shrink-0 image_6"
	  			              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16914818924064398945.png"
	  			            />
	  			            <text class="self-center font_2">运动中</text>
	  			          </view>
	  			        </view> -->
	  					<!-- <view class="flex-row justify-between equal-division">
	  					  <view class="flex-row equal-division-item_2 space-x-4">
	  					    <image
	  					      class="shrink-0 image_6"
	  					      src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16914818924074625101.png"
	  					    />
	  					    <text class="self-center font_2">等天晴</text>
	  					  </view>
	  					  <view class="flex-row equal-division-item_2 space-x-4">
	  					    <image
	  					      class="shrink-0 image_6"
	  					      src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16914818924094761713.png"
	  					    />
	  					    <text class="self-center font_2">社交中</text>
	  					  </view>
	  					</view> -->
	  			      </view>
	  					
	  					
	  			    </view>
	  			  </view>
	  			
	  			</view>
	              <!-- <image class="imageV" :src="mySrc"></image> -->
	  
	              <!-- <button style="width: 80%; height: 48px;margin-top: 20px; background-color: seagreen;color: white;"> 确定
	              </button> -->
	  			
	          </view>
	          <!-- 自定义关闭按钮 -->
	          <view class="close" @click="isshow=false">✕</view>
	      </cc-popup>
	  
	  </view>
	  
    </view>

  </view>
</template>

<script>
  export default {
    components: {},
    data() {
      return {
			emojiList:[
					{ url: '../../static/liaoyiliao4.png', name: '想聊天' },
					{ url: '../../static/moyu2.png', name: '摸鱼中' },
					{ url: 'https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16914818924048861981.png', name: '约咖啡' },
					{ url: '../../static/fangzi.png', name: '想回家' },
					{ url: '../../static/kaixin2.png', name: '心情好' },
					{ url: 'https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16914818924064398945.png', name: '运动中' },
					{ url: 'https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16914818924074625101.png', name: '等天晴' },
					{ url: '../../static/jiaoliu2.png', name: '社交中' },
					
				],		  
		  // selectedEmoji:'',
		  selectedEmoji: { url: '', name: '我的状态' },
		  title: 'Hello',
		  companyList: [{}, {}, {}],
		  isshow: false,
		  mySrc: '../../static/apple.jpg',
		  nextname:"",
		  nexturl:"",
		  currentIndex: 0, // 当前要添加的元素在arrList1中的索引
		  arrList: [
		    {
		      id: 1,
		      url: "../../static/tx11.jpeg",
		      name: '新朋友',
		      msg: 'OK',
		    },
		    {
		      id: 2,
		      url: "../../static/tx14.jpeg",
		      name: '好爱笑',
		      msg: '没关系的',
		    },
			{
			  id: 3,
			  url: "../../static/tx12.jpeg",
			  name: '小雨',
			  msg: '明天去哪里玩？',
			},
			{
			  id: 4,
			  url: "../../static/tx15.jpeg",
			  name: '圆圆',
			  msg: '到时候一起去参加活动吧~',
			},
			{
			  id: 5,
			  url: "../../static/tx13.jpeg",
			  name: '若楠',
			  msg: '不见不散哦',
			},
		  ],
		  arrList1: [
		    {
		      id: 6,
		      url: "../../static/tx16.jpeg",
		      name: '小曲奇',
		      msg: '我们已经是好友了，现在可以开始...',
		    },
		    {
		      id: 7,
		      url: "../../static/tx17.jpeg",
		      name: '快乐小猫',
		      msg: '我们已经是好友了，现在可以开始...',
		    },
			{
			  id: 8,
			  url: "../../static/tx18.jpeg",
			  name: '小晨',
			  msg: '我们已经是好友了，现在可以开始...',
			},
			{
			  id: 9,
			  url: "../../static/tx19.jpeg",
			  name: '梦想家',
			  msg: '我们已经是好友了，现在可以开始...',
			},
			{
			  id: 10,
			  url: "../../static/tx20.jpeg",
			  name: '自由飞翔',
			  msg: '我们已经是好友了，现在可以开始...',
			},
		  ],
	  };
    },
    methods: {
		    selectEmoji(emoji) {
		      this.selectedEmoji.url = emoji.url;
		      this.selectedEmoji.name = this.getEmojiName(emoji);
		    },
		    getEmojiName(emoji) {
		      // 根据表情获取对应的名称
		      return emoji.name;
		    },
		// selectEmoji(emoji) {
		//     this.selectedEmoji = emoji.url;
		// // uni.setStorageSync('selectedEmoji', emoji); // 将选择的表情保存到本地存储
		//   },
		popupClick() {
		    
		    this.isshow = !this.isshow;
		},
		gochat(item){
			console.log(item.name);
			console.log(item.url);
			console.log(item.id);
			uni.navigateTo({
				url:"/pages/chat/chat?name=" + item.name + '&url=' + encodeURIComponent(item.url) + "&id=" + item.id
			})
		},
		gotxl(){
			uni.navigateTo({
				url:"/pages/txl/txl"
			})
		},
		goTXLadd(){
			uni.navigateTo({
				url:"/pages/TXLadd/TXLadd"
			})
		},
		gopipei(){
			if (this.currentIndex < this.arrList1.length) {
			const nextElement = this.arrList1[this.currentIndex];
			console.log(nextElement.name);
			this.nextname=nextElement.name
			this.nexturl=nextElement.url
			this.arrList.push(nextElement);
			this.currentIndex++;
		  }
			uni.navigateTo({
				//url:`/pages/pipei/pipei?name=${nextElement.name}`
				url:"/pages/pipei/pipei?name=" + this.nextname + '&url=' + encodeURIComponent(this.nexturl)
			})
		},
		loadData() {
			//localStorage.clear();//此处取消缓存
			const storedArrList = localStorage.getItem("arrList");
			if (storedArrList) {
			  this.arrList = JSON.parse(storedArrList);
			}
		},
		  saveData() {
			localStorage.setItem("arrList", JSON.stringify(this.arrList));
		}
	},
	mounted() {
	      this.loadData();
	      window.addEventListener("beforeunload", this.saveData);
	    },
	beforeDestroy() {
	  this.saveData();
	  window.removeEventListener("beforeunload", this.saveData);
	}
  };
</script>

<style scoped lang="scss">
	.dingwei{
		display: inline-block;
		line-height: 155rpx;
		
	}
	.weizhi{
		position: absolute;
            right: 215rpx;
            top: 57rpx;
	}
	.content {
	      display: flex;
	      flex-direction: column;
	
	  }
	  .modelContent {
	      width: 100%;
	      height: 100%;
	      display: flex;
	      align-items: center;
	      flex-direction: column;
			background-image: linear-gradient(180deg, #c9dfff 0%, #ffffff 100%);
			border-radius: 30rpx;
	  }
	
	  .imageV {
	
	      margin-top: 0px;
	      width: calc(100vw - 100px);
	      height: calc((100vw - 100px) * 0.567);
	  }
	
	  .close {
	      width: 60rpx;
	      height: 60rpx;
	      color: #FFFFFF;
	      line-height: 60rpx;
	      text-align: center;
	      border-radius: 50%;
	      border: 1px solid #FFFFFF;
	      position: relative;
	      bottom: +20%;
	      left: 50%;
	      transform: translate(-50%, -50%);
	  }
	  .container {
			display: flex;
			flex-wrap: wrap;
			}
	  .image-container:hover image {
	              transform: scale(1.3);  
	              transition: all 1s ease 0s;  
	              -webkit-transform: all 1s ease 0s;  
	              -webkit-transform: scale(1.3); /*放大1.3倍*/
	  			transition-duration: .5s;
	  			overflow:hidden;
	  }
	  .pig {
	    .grass {
	      .group_3 {
	        margin: -25rpx 0 -26rpx;
	  		margin-right: 761rpx;
	        // padding-top: 20rpx;
	        // .section_3 {
	        //   margin: 0 40rpx;
	        //   padding: 0rpx 26rpx 0;
	        //   background-color: #f5f5f5;
	        //   border-radius: 24rpx 24rpx 0 0;
	        // }
	        .section_2 {
				margin-left: 30rpx;
	  			width: 620rpx;
	  			height: 450rpx;
	          padding: 40rpx 60rpx 120rpx 90rpx;
	          background-image: linear-gradient(180deg, #c9dfff 0%, #ffffff 100%);
	          border-radius: 40rpx;
	          // box-shadow: 0px 8rpx 16rpx #00000029;
	          .group_4 {
	            padding-left: 60rpx;
	            .space-x-8 {
	              & > view:not(:first-child),
	              & > text:not(:first-child),
	              & > image:not(:first-child) {
	                margin-left: 16rpx;
	              }
	            }
	          }
	          .equal-division-item_2 {
	            padding: 25rpx 0;
	            .image_5 {
	              width: 49rpx;
	              height: 49rpx;
	            }
	            .image_6 {
	              width: 50rpx;
	              height: 50rpx;
	            }
	          }
	          .space-x-6 {
	            & > view:not(:first-child),
	            & > text:not(:first-child),
	            & > image:not(:first-child) {
	              margin-left: 12rpx;
	  			  margin-right: 50rpx;
	            }
	          }
	          .font_2 {
	            font-size: 40rpx;
	            font-family: SegoeUI;
	            line-height: 44rpx;
	            color: #838383;
	          }
	          .equal-division {
	            margin-left: 6rpx;
	            .space-x-4 {
	              & > view:not(:first-child),
	              & > text:not(:first-child),
	              & > image:not(:first-child) {
	                margin-left: 8rpx;
	  				margin-right: 50rpx;
	              }
	            }
	          }
	          .image_7 {
	            width: 58rpx;
	            height: 51rpx;
	          }
	        }
	        .space-y-84 {
	          & > view:not(:first-child),
	          & > text:not(:first-child),
	          & > image:not(:first-child) {
	            margin-top: 100rpx;
	  
	          }
	        }
	        .pos_2 {
	          position: absolute;
	          left: 40rpx;
	          right: 40rpx;
	          top: 0;
	        }
	      }
	      
	      .image {
	        width: 48rpx;
	        height: 48rpx;
	      }
	  	  .image8 {
	  	    width: 50rpx;
	  	    height: 45rpx;
	  	  }
	    }
	    
	    
	  }
  .page {
	  position: fixed;
    //background-color: #ffffff;
	background-image: linear-gradient(180deg, #ccf0f0 0%, #eff0ff 21.4%, #deecff 48.5%, #eff0ff 76.7%, #ccf0f0 100%);
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .group {
      overflow-y: auto;
      .section {
        padding: 15rpx 48rpx 228rpx;
        //background-color: #65cbc8;
        .group_2 {
          padding: 0 58rpx;
          .text-wrapper {
            margin: 4rpx 0;
            padding: 12rpx 0;
            background-color: #ffffff;
            border-radius: 26rpx;
            box-shadow: 0px 10rpx 8rpx #9695a129;
            width: 450rpx;
            height: 60rpx;
            .text {
			  margin: auto 0;
              margin-left: 44rpx;
              color: #d4d0d0;
              font-size: 20rpx;
              font-family: SegoeUI;
            }
          }
          .image {
            margin-left: 10rpx;
            width: 48rpx;
            height: 48rpx;
          }
		  .image1 {
		    margin-right: 10rpx;
		    width: 48rpx;
		    height: 48rpx;
		  }
          .image_2 {
            margin-left: 20rpx;
            width: 42rpx;
            height: 40rpx;
          }
        }
      }
      .space-y-13 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 26rpx;
        }
      }
      .section_2 {
        margin: -200rpx 40rpx -174rpx;
        padding: 28rpx 26rpx 28rpx;
		height: 100%;
        background-color: #ffffff;
		border-radius: 30rpx;
        background-size: 100% 100%;
        background-repeat: no-repeat;
        .text_2 {
          color: #202020;
          font-size: 40rpx;
          font-family: SegoeUI-Bold;
          font-weight: 700;
          line-height: 37rpx;
		  
        }
      }
      .space-y-11 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 28rpx;
        }
      }
      .space-x-14 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
			
          margin-left: 28rpx;
        }
        .equal-division-item {
          flex: 1 1 314rpx;
          //padding: 96rpx 0 88rpx;
          filter: drop-shadow(0px 6rpx 6rpx #00000029);
		  background-color: #fff0eb;
		  //background-image: radial-gradient(37.8% 37.8% at 77.9% 33.6%, #d5e7ff 0%, #ffffff 100%);
		  //background-image: linear-gradient(180deg, #ffe4dd 0%, #ffffff 100%);
		  // background: linear-gradient(
		  //     to bottom right, 
		  //     #fbffde 0%,
		  //     #fffbe1 20%,
		  //     #fff4e0 40%,
		  //     #ffe7cf 60%,
		  //     #ffe6cd 80%,
		  //     #f9d4ca 100%
		  //   );
		  background-image: linear-gradient(180deg, #ffe4dd 0%, #ffffff 100%);
		  // background: linear-gradient(
		  //     to bottom right, 
		  //     #ffffff 0%,
		  //     #fff6f3 20%,
		  //     #fffaf6 40%,
		  //     #fff2e1 60%,
		  //     #ffecdd 80%,
		  //     #f9cdbe 100%
		  //   );
		  //background-image: url(../../static/xinqiu.jpg);
		  border-radius: 60rpx;
          background-size: 100% 100%;
          background-repeat: no-repeat;
          height: 150rpx;
          .font_1 {
			  
            font-size: 40rpx;
            font-family: SegoeUI;
            //line-height: 120rpx;
			margin: auto auto;
			font-weight: 700;
            color: #535766;
			padding-left: 3rpx;
          }
		  .font_2 {

		    font-size: 40rpx;
		    font-family: SegoeUI;
		    //line-height: 120rpx;
		  		padding-left: 10rpx;
		  		font-weight: 700;
		    color: #535766;
		  }
          .image_3 {
            width: 25rpx;
            height: 25rpx;
          }
		  .image_4 {

		    width: 45rpx;
		    height: 40rpx;
			
		  }
          .pos {
            position: absolute;
            right: 30rpx;
            top: 24rpx;
          }
        }
		.bj{
			background-image: linear-gradient(180deg, #c9dfff 0%, #ffffff 100%);
		}
        .section_3 {
          background-color: #d4d0d0;
          border-radius: 50%;
          width: 104rpx;
          height: 104rpx;
		  overflow: hidden;
		  image
		  {
			  width: 104rpx;
			  height: 104rpx;
		  }
        }
        .space-y-8 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 16rpx;
          }
          .space-x-8 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 16rpx;
            }
          }
        }

        .font_2 {
          font-size: 32rpx;
          font-family: SegoeUI;
          line-height: 30rpx;
          color: #202020;
        }
        .font_3 {
          font-size: 28rpx;
          font-family: SegoeUI;
          line-height: 26rpx;
          color: #838383;
        }
      }
    }
  }
</style>