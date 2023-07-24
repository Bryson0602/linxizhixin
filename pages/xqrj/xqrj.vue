<template>
	<view class="flex-col page content">
    <view class="flex-row justify-between items-center section">
      <!-- <view class="flex-col justify-start items-center text-wrapper"><text class="font_1 text">0</text></view> -->
      <view class="flex-col justify-start items-center text-wrapper"><text class="font_1 text text_3">{{dateFormat1(date)}}</text></view>
      <text class="font_2 text text_4">月</text>
      <!-- <view class="flex-col justify-start items-center text-wrapper"><text class="font_1 text">0</text></view> -->
      <view class="flex-col justify-start items-center text-wrapper"><text class="font_1 text">{{dateFormat2(date)}}</text></view>
      <text class="font_2 text text_5">日</text>
      <!-- <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_1 text">1</text></view> -->
      <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_1 text">{{dateFormat3(date)}}</text></view>
      <text class="font_3 text text_6">时</text>
      <!-- <view class="flex-col justify-start items-center text-wrapper"><text class="font_1 text">3</text></view> -->
      <view class="flex-col justify-start items-center text-wrapper"><text class="font_1 text">{{dateFormat4(date)}}</text></view>
      <text class="font_3 text text_7">分</text>
    </view>
    <view class="flex-col justify-start text-wrapper_3 ">
      <text class="font_4 text text_8">我想你发烫的手机需要冷静一下~</text>
    </view>
    <view class="flex-col group">
      <view class="flex-col justify-start self-center text-wrapper_4">
        <text class="text_9">做人嘛，开心最重要啦~</text>
      </view>
	  <!-- <image class="self-center tupian" src="../../static/bqb8.png" mode=""></image> -->
	  <image
	    class="self-center tupian"
	    :src="selectedEmoji"
	  />
	  <view class="content">
	  
	          <!-- <view class="popUpBtn" @click="popupClick">
	              点击显示弹框</view> -->
	  
	          <!-- 使用组件 isShow：设置弹框是否显示 width：宽度 height：高度 radius：圆角 -->
	          <cc-popup :isShow='isshow' width="650rpx" height="600rpx" radius="50rpx">
	  			<!-- calc(100vw - 70px) -->
	              <!-- 自定义展示内容 -->
	        <view class="modelContent">	
      <view class="flex-col relative section_2 space-y-10">
        <view class="flex-row justify-between items-start group_2">
          <text class="text_10">每日心情</text>
          <!-- <text class="font_5 text_11">今天的你是哪一种呢</text> -->
        </view>
		
        <view class="grid">
          <view class="flex-col items-center grid-item space-y-4 image-container" v-for="(emoji, index) in emojiList" :key="index">
				<image
              class="image xuanting"
              :src="emoji.url"
			  @click="selectEmoji(emoji)"
            />
			<!-- <image
			  v-for="(emoji, index) in emojiList" :key="index" :src="emoji" @click="selectEmoji(emoji)"
			></image> -->
		
		<text class="font_5" >{{emoji.name}}</text>
           
          </view>
          <!-- <view class="flex-col items-center grid-item space-y-4">
            <image
              class="image"
              src="../../static/bqb5.png"
            />
            <text class="font_5">无语</text>
          </view>
          <view class="flex-col items-center grid-item space-y-4">
            <image
              class="image"
              src="../../static/bqb6.png"
            />
            <text class="font_5">难过</text>
          </view>
          <view class="flex-col items-center grid-item space-y-4">
            <image
              class="image"
              src="../../static/bqb1.png"
            />
            <text class="font_5">思考</text>
          </view>
          <view class="flex-col items-center grid-item space-y-4">
            <image
              class="image"
              src="../../static/bqb7.png"
            />
            <text class="font_5">生气</text>
          </view>
          <view class="flex-col items-center grid-item space-y-4">
            <image
              class="image"
              src="../../static/bqb3.png"
            />
            <text class="font_5">得瑟</text>
          </view>
          <view class="flex-col items-center grid-item space-y-4">
            <image
              class="image"
              src="../../static/bqb2.png"
            />
            <text class="font_5">惊讶</text>
          </view>
          <view class="flex-col items-center grid-item space-y-4">
            <image
              class="image"
              src="../../static/bqb8.png"
            />
            <text class="font_5">心动</text>
          </view> -->
        </view>
      </view>
	  </view>
	          <!-- 自定义关闭按钮 -->
	    <view class="close" @click="isshow=false">✕</view>
	    </cc-popup>
	  
	  </view>
	  
      <view class="flex-row items-center self-center section_3 space-x-2" @click="popupClick">
        <view class="section_4"></view>
        <text class="font_3 text text_12" >换个心情</text>
      </view>
    </view>
    <view class="flex-row group_3 space-x-8">
		
      <view class="flex-col justify-start items-center flex-auto text-wrapper_5">
        <!-- <text class="font_4 text_14">随手记录心情吧~</text> -->
		<input type="text" value="随手记录心情吧~" class="font_4 text_14">
      </view>
	  
      <view class="flex-col justify-start items-center shrink-0 text-wrapper_6" @click="clickjl">
        <text class="font_4 text text_13">快速记录</text>
      </view>
    </view>
  </view>
  
  
</template>

<script>
  export default {
    components: {},
    data() {
      return {
		  date: new Date().toISOString(),	
		  title: 'Hello',
		  companyList: [{}, {}, {}],
		  isshow: false,
		  // mySrc: '../../static/apple.jpg',
			emojiList:[
					// {img:require('../../static/bqb4.png'),text:'开心'},
					// {img:'../../static/bqb5.png',text:'无语'},
					// {img:'../../static/bqb6.png',text:'难过'},
					// {img:'../../static/bqb1.png',text:'思考'},
					// {img:'../../static/bqb7.png',text:'生气'},
					// {img:'../../static/bqb3.png',text:'得瑟'},
					// {img:'../../static/bqb2.png',text:'惊讶'},
					// {img:'../../static/bqb8.png',text:'心动'},
					{ url: '../../static/bqb4.png', name: '开心' },
					{ url: '../../static/bqb5.png', name: '无语' },
					{ url: '../../static/bqb6.png', name: '难过' },
					{ url: '../../static/bqb1.png', name: '思考' },
					{ url: '../../static/bqb7.png', name: '生气' },
					{ url: '../../static/bqb3.png', name: '得瑟' },
					{ url: '../../static/bqb2.png', name: '惊讶' },
					{ url: '../../static/bqb8.png', name: '心动' },
					
		   ],
		  // emojiList: ['../../static/bqb4.png', '../../static/bqb5.png', '../../static/bqb6.png','../../static/bqb1.png','../../static/bqb7.png','../../static/bqb3.png','../../static/bqb2.png','../../static/bqb8.png'],
		  // textList: ['开心','无语','难过','思考','生气','得瑟','惊讶','心动'],
		   // 表情图片路径列表
		  selectedEmoji: '', // 存储选择的表情图片路径
	  };
    },
	onLoad(){
		let _this = this;
		setInterval(function() {
		_this.date = Date.parse(new Date());
		}, 1000);
	},
	
    methods: {
		selectEmoji(emoji) {
		  this.selectedEmoji = emoji.url;
		},
		clickjl(){
			uni.showToast({
			title: '提交成功',
			duration: 1000
			});
		},
		popupClick() {
		
		    this.isshow = !this.isshow;
		},
		dateFormat1(time) {
			let date = new Date(time);
			let year = date.getFullYear();
			// 在日期格式中，月份是从0开始的，因此要加0，使用三元表达式在小于10的前面加0，以达到格式统一  如 09:11:05
			let month = date.getMonth() + 1 < 10 ? "0" + (date.getMonth() + 1) : date.getMonth() + 1;
			let day = date.getDate() < 10 ? "0" + date.getDate() : date.getDate();
			let hours = date.getHours() < 10 ? "0" + date.getHours() : date.getHours();
			let minutes = date.getMinutes() < 10 ? "0" + date.getMinutes() : date.getMinutes();
			let seconds = date.getSeconds() < 10 ? "0" + date.getSeconds() : date.getSeconds();
			// 拼接
			return month
			// return year + "-" + month + "-" + day;
		},
		dateFormat2(time) {
			let date = new Date(time);
			let year = date.getFullYear();
			// 在日期格式中，月份是从0开始的，因此要加0，使用三元表达式在小于10的前面加0，以达到格式统一  如 09:11:05
			let month = date.getMonth() + 1 < 10 ? "0" + (date.getMonth() + 1) : date.getMonth() + 1;
			let day = date.getDate() < 10 ? "0" + date.getDate() : date.getDate();
			let hours = date.getHours() < 10 ? "0" + date.getHours() : date.getHours();
			let minutes = date.getMinutes() < 10 ? "0" + date.getMinutes() : date.getMinutes();
			let seconds = date.getSeconds() < 10 ? "0" + date.getSeconds() : date.getSeconds();
			// 拼接
			return  day;
			// return year + "-" + month + "-" + day;
		},
		dateFormat3(time) {
			let date = new Date(time);
			let year = date.getFullYear();
			// 在日期格式中，月份是从0开始的，因此要加0，使用三元表达式在小于10的前面加0，以达到格式统一  如 09:11:05
			let month = date.getMonth() + 1 < 10 ? "0" + (date.getMonth() + 1) : date.getMonth() + 1;
			let day = date.getDate() < 10 ? "0" + date.getDate() : date.getDate();
			let hours = date.getHours() < 10 ? "0" + date.getHours() : date.getHours();
			let minutes = date.getMinutes() < 10 ? "0" + date.getMinutes() : date.getMinutes();
			let seconds = date.getSeconds() < 10 ? "0" + date.getSeconds() : date.getSeconds();
			// 拼接
			return  hours ;
			// return year + "-" + month + "-" + day;
		},
		dateFormat4(time) {
			let date = new Date(time);
			let year = date.getFullYear();
			// 在日期格式中，月份是从0开始的，因此要加0，使用三元表达式在小于10的前面加0，以达到格式统一  如 09:11:05
			let month = date.getMonth() + 1 < 10 ? "0" + (date.getMonth() + 1) : date.getMonth() + 1;
			let day = date.getDate() < 10 ? "0" + date.getDate() : date.getDate();
			let hours = date.getHours() < 10 ? "0" + date.getHours() : date.getHours();
			let minutes = date.getMinutes() < 10 ? "0" + date.getMinutes() : date.getMinutes();
			let seconds = date.getSeconds() < 10 ? "0" + date.getSeconds() : date.getSeconds();
			// 拼接
			return minutes;
			// return year + "-" + month + "-" + day;
		}
	},
  };
</script>

<style scoped lang="scss">
  .page {
    padding: 44rpx 32rpx 62rpx;
    background-image: linear-gradient(180deg, #bdf5f0 0%, #f2f2e8 26.4%, #e8f5f4 51.1%, #59d5d3 100%);
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
	position: fixed;
    .text {
      // opacity: 0.7;
    }
    .text_2 {
      color: #202020;
      font-size: 40rpx;
      font-family: SegoeUI;
      line-height: 37rpx;
    }
    .section {
      margin: 30rpx 8rpx 0;
      padding: 16rpx 32rpx;
      background-color: #7bdddbb3;
      border-radius: 24rpx;
      .text-wrapper {
        padding: 16rpx 0;
        background-color: #ffffffb3;
        border-radius: 24rpx;
        width: 46rpx;
        height: 64rpx;
		text-align: center;
        .text_3 {
          line-height: 28rpx;
        }
      }
      .font_2 {
        font-size: 36rpx;
        font-family: SegoeUI-Bold;
        line-height: 29rpx;
        font-weight: 700;
        color: #ffffff;
      }
      .text_4 {
        line-height: 31rpx;
      }
      .text_5 {
        line-height: 30rpx;
      }
      .text-wrapper_2 {
        padding: 16rpx 0;
        background-color: #ffffffb3;
        border-radius: 24rpx;
        width: 48rpx;
        height: 64rpx;
      }
      .font_1 {
        font-size: 36rpx;
        font-family: SegoeUI-Bold;
        line-height: 29rpx;
        font-weight: 700;
        color: #59a09e;
      }
      .text_6 {
        font-size: 34rpx;
        line-height: 31rpx;
      }
      .text_7 {
        font-size: 34rpx;
        line-height: 31rpx;
      }
    }
    .text-wrapper_3 {
      margin-right: 16rpx;
      margin-top: 52rpx;
      padding: 35rpx 0 28rpx;
      background-color: #ffffffb3;
      border-radius: 60rpx;
      box-shadow: 0px 6rpx 12rpx #a1a1a129;
      .text_8 {
        margin-left: 44rpx;
        margin-right: 32rpx;
        color: #51c5c3;
      }
    }
    .group {
      margin-top: 96rpx;
      padding: 0 8rpx;
      height: 746rpx;
      .text-wrapper_4 {
        padding: 52rpx 0 92rpx;
        // opacity: 0.7;
        background-image: url('https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385923714170159.png');
        background-size: 100% 100%;
        background-repeat: no-repeat;
        width: 528rpx;
        .text_9 {
          margin-left: 32rpx;
          margin-right: 16rpx;
          color: #343434;
          font-size: 44rpx;
          font-family: SegoeUI-Bold;
          font-weight: 700;
          line-height: 42rpx;
        }
      }
      .section_2 {
        margin: 55rpx auto;
        padding: 10rpx 0;
        filter: drop-shadow(0px 6rpx 6rpx #00000029);
        // background-image: url('https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385868940833479.png');
        background-size: 100% 100%;
        background-repeat: no-repeat;
        .group_2 {
          padding: 0 32rpx;
          .text_10 {
            color: #1e1c1c;
            font-size: 48rpx;
            font-family: SegoeUI-Bold;
            font-weight: 700;
            line-height: 44rpx;
          }
          .text_11 {
			margin-left: 50rpx;
            margin-right: 4rpx;
            margin-top: 28rpx;
            color: #202020;
            line-height: 30rpx;
          }
        }
        .grid {
          padding: 0 14rpx;
          height: 324rpx;
          display: grid;
          grid-template-columns: repeat(4, 1fr);
          .grid-item {
            padding: 4rpx 0;
            .image {
              width: 160rpx;
              height: 160rpx;
			  
			  // 125 125
            }
          }
          .space-y-4 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-top: 8rpx;
            }
          }
        }
        .font_5 {
          font-size: 20rpx;
		  // (32rpx)
          font-family: SegoeUI-Bold;
          line-height: 29rpx;
          font-weight: 700;
          color: #1e1c1c;
        }
      }
      .space-y-10 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 20rpx;
        }
      }
      .section_3 {
        margin-top: 0rpx;
        padding: 4rpx 16rpx 10rpx;
        background-color: #ffffff59;
        border-radius: 60rpx;
        .section_4 {
          background-color: #00000000;
          width: 72rpx;
          height: 72rpx;
        }
        .text_12 {
          margin-right: 36rpx;
          line-height: 30rpx;
        }
      }
      .space-x-2 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 4rpx;
        }
      }
	  .tupian{
	  	width: 600rpx;
	  	height: 600rpx;
	  }
    }
    .font_3 {
      font-size: 34rpx;
      font-family: SegoeUI-Bold;
      line-height: 29rpx;
      font-weight: 700;
      color: #ffffff;
      padding-right: 25rpx;
    }
    .group_3 {
      margin-top: 224rpx;
      padding: 0 8rpx;
      .text-wrapper_5 {
        padding: 25rpx 0 20rpx;
        // opacity: 0.7;
        border-radius: 60rpx;
        height: 102rpx;
		border: 1rpx solid white;
		
        .text_14 {
          color: #ffffff;
		  
        }
      }
      .text-wrapper_6 {
        padding: 32rpx 0;
        background-color: #ffffffb3;
        border-radius: 60rpx;
        width: 230rpx;
        height: 102rpx;
        .text_13 {
          color: #7bdddb;
        }
      }
    }
    .space-x-8 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-left: 16rpx;
      }
    }
    .font_4 {
      font-size: 38rpx;
      font-family: SegoeUI-Bold;
      line-height: 37rpx;
      font-weight: 700;
	  text-align: center;
	  
    }
  }
  .content {
        display: flex;
        flex-direction: column;
  
    }
  
  //   .popUpBtn {
  //       height: 80rpx;
  //       line-height: 80rpx;
  //       width: 320rpx;
  //       margin-top: 120rpx;
  //       margin-left: auto;
  //       margin-right: auto;
  //       margin-bottom: 50rpx;
  //       background-color: bisque;
  //       text-align: center;
  		// background-color: pink;
  //   }
  
    .modelContent {
        width: 100%;
        height: 100%;
        display: flex;
        align-items: center;
        flex-direction: column;
  		background-image: linear-gradient(rgb(223,233,254), white);
  		border-radius: 50rpx;
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
        bottom: -10%;
        left: 50%;
        transform: translate(-50%, -50%);
    }
	// .image-container:hover image{
	//             box-shadow: 0 0 10px rgba(0, 0, 0, 0.5); /* 调整阴影效果的大小和颜色 */
	//         }
	 .image-container:hover image {
	            transform: scale(1.3);  
	            transition: all 1s ease 0s;  
	            -webkit-transform: all 1s ease 0s;  
	            -webkit-transform: scale(1.3); /*放大1.3倍*/
				transition-duration: .5s;
				overflow:hidden;
	}
	// .xuanting:hover{
	// 	transform: scale(1.3);  
	// 	transition: all 0.5s ease 0s;  
	// 	-webkit-transform: scale(1.3);  
	// 	-webkit-transform: all 0.5s ease 0s;  
	// }
</style>