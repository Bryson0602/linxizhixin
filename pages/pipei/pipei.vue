<template>
  <view class="flex-col page space-y-48">
    <view class="flex-row relative group" v-if="matchingStatus !== 'success'">
		<image
		  class="image_3 pos_8"
		  src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385900488393988.png"
		/>
		<image
		  class="image_2 pos_5"
		  src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385900804906345.png"
		/>
		<image
		  class="image pos_3"
		  src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16908596901210179158.png"
		/>
      <view class="section_6 pos_10">
		  <image src="../../static/lxzx.png" mode=""></image>
	  </view>
      <view class="section_2 pos_4">
		  <image src="../../static/tx3.jpg" mode=""></image>
	  </view>
      <view class="section_9 pos_13">
		  <image src="../../static/tx4.jpeg" mode=""></image>
	  </view>
      <view class="section_3 pos_6">
		  <image src="../../static/tx5.jpeg" mode=""></image>
	  </view>
      <view class="section_10 pos_14">
		  <image src="../../static/tx6.jpeg" mode=""></image>
	  </view>
      <view class="section_4 pos_7">
		  <image src="../../static/tx7.jpeg" mode=""></image>
	  </view>
      <view class="section pos_2">
		  <image src="../../static/tx2.jpg" mode=""></image>
	  </view>
      <view class="section_11 pos_15">
		  <image src="../../static/tx8.jpeg" mode=""></image>
	  </view>
      <view class="section_8 pos_12">
		  <image src="../../static/tx9.jpeg" mode=""></image>
	  </view>
      <view class="section_7 pos_11">
		  <image src="../../static/tx1.jpg" mode=""></image>
	  </view>
      <view class="section_5 pos_9">
		  <image src="../../static/tx10.jpeg" mode=""></image>
	  </view>
      
      <!-- <view class="flex-col justify-start items-end text-wrapper pos">
        <text class="text">星球越大匹配概率越高哦...</text>
      </view> -->
    </view>
	
	<view class="flex-row self-center relative group" v-else>
		<view class="flex-row justify-between page1">
		  <view class="flex-col items-center group_2">
		    <text class="font_1">小灵</text>
			<view class="section">
				<image src="../../static/lxzx.png" mode=""></image>
			</view>
		  </view>
		  <view class="flex-col items-center group_2">
		    <text class="font_1">{{this.name}}</text>
		    <view class="section">
				<image :src="url" mode=""></image>
			</view>
		  </view>
		</view>
	</view>
	
	
	<view class="load_14 self-center">
		<view class="bounce1"></view>
		<view class="bounce2"></view>
		<view class="bounce3"></view>
	</view>
	<text class="flex-col justify-start items-center self-center text_2" v-if="matchingStatus === 'matching'">
		正在匹配中...
	</text>
	<text class="flex-col justify-start items-center self-center text_2" v-else-if="matchingStatus === 'analyzing'">
		正在分析MBTI...
	</text>
	<text class="flex-col justify-start items-center self-center text_2" v-else-if="matchingStatus === 'fxing'">
		分析完成...
	</text>
	<text class="flex-col justify-start items-center self-center text_2" v-else-if="matchingStatus === 'success'">
		匹配成功！
	</text>
	
    <view class="flex-col justify-start items-center self-center text-wrapper_2"v-if="matchingStatus === 'success'" @click="gochat">
		<text>开始聊天</text>
    </view>
  </view>
</template>

<script>
  export default {
    components: {},
    data() {
      return {
		  name:'',
		  url:"",
		  matchingStatus: 'matching'
	  };
    },
	  mounted() {
	    setTimeout(() => {
	      this.matchingStatus = 'analyzing';
	    }, 2000);
		setTimeout(() => {
		  this.matchingStatus = 'fxing';
		}, 3500);
	    setTimeout(() => {
	      this.matchingStatus = 'success';
	    }, 5000);
	  },
    methods: {
		gochat(){
			uni.redirectTo({
				url:"/pages/chat/chat?name=" + this.name + '&url=' + encodeURIComponent(this.url)
			})
		}
	},
	onLoad(option) {
		//接受信息
		const name = option.name;
		const url = option.url;
		console.log(option.url);
		this.name = name;
		this.url = url;
	},
  };
</script>

<style scoped lang="scss">
	@keyframes floating {
	  0% {
	    transform: translateY(0);
	  }
	  50% {
	    transform: translateY(-10px);
	  }
	  100% {
	    transform: translateY(0);
	  }
	}
	@keyframes floating1 {
	  0% {
	    transform: translateY(0);
	  }
	  50% {
	    transform: translateY(10px);
	  }
	  100% {
	    transform: translateY(0);
	  }
	}
  .page {
	  
	  
	  position: fixed;
    padding: 100rpx 0 100rpx;
	background-image: linear-gradient(180deg, #4f4f66 0%, #3c4755 21.4%, #4e595e 48.5%, #342b43 76.7%, #243e3a 100%);
	//background-image: linear-gradient(180deg, #ccf0f0 0%, #eff0ff 21.4%, #deecff 48.5%, #eff0ff 76.7%, #ccf0f0 100%);
    background-size: 100% 100%;
    background-repeat: no-repeat;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
	
	.page1 {
	  //padding: 452rpx 64rpx 260rpx;
	  //background-color: #eac6ff;
	  //background-image: url('https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16908596901255817602.png');
	  //background-size: 100% 100%;
	  // background-repeat: no-repeat;
	  // width: 100%;
	  // overflow-y: auto;
	  // overflow-x: hidden;
	  //height: 100%;
	  // .group1 {
	  //   padding-left: 54rpx;
	  //   padding-right: 54rpx;
	  // }
	  .group_2 {
	    margin-top: 64rpx;
		padding-left: 54rpx;
		padding-right: 54rpx;
	    .section {
	      //flex: 1 1 290rpx;
		  margin-top: 64rpx;
	      background-color: #e0e0e0;
	      border-radius: 50%;
	      width: 230rpx;
	      height: 230rpx;
		  overflow: hidden;
		  image{
			  width: 230rpx;
			  height: 230rpx;
		  }
	    }
	  }
	  .font_1 {
	    font-size: 52rpx;
	    font-family: SegoeUI;
	    line-height: 48rpx;
	    color: #ffffff;
	  }
	}
	
	// -------------------------------------------------
    .group {
      padding: 40rpx 66rpx 16rpx;
      overflow-x: hidden;
      height: 866rpx;
	  
      .section_6 {
        background-color: #e0e0e0;
        border-radius: 50%;
        width: 190rpx;
        height: 190rpx;
		overflow: hidden;
		image{
			width: 190rpx;
			height: 190rpx;
		}
      }
      .pos_10 {
        position: absolute;
        right: 270rpx;
        top: 347rpx;
      }
      .section_2 {
        background-color: #e0e0e0;
        border-radius: 50%;
        width: 82rpx;
        height: 84rpx;
		overflow: hidden;
		image{
			width: 82rpx;
			height: 84rpx;
		}
      }
      .pos_4 {
        position: absolute;
        left: 180rpx;
        top: 201rpx;
		animation: floating 2s infinite ease-in-out;
      }
      .section_9 {
        background-color: #e0e0e0;
        border-radius: 50%;
        width: 52rpx;
        height: 52rpx;
		overflow: hidden;
		image{
		  width: 52rpx;
		  height: 52rpx;
		}
      }
      .pos_13 {
        position: absolute;
        right: 66rpx;
        top: 647rpx;
      }
      .section_3 {
        background-color: #e0e0e0;
        border-radius: 50%;
        width: 56rpx;
        height: 54rpx;
		overflow: hidden;
		image{
		  width: 56rpx;
		  height: 54rpx;
		}
      }
      .pos_6 {
        position: absolute;
        right: 270rpx;
        top: 261rpx;
      }
      .section_10 {
        background-color: #e0e0e0;
        border-radius: 50%;
        width: 72rpx;
        height: 70rpx;
		overflow: hidden;
		image{
		  width: 72rpx;
		  height: 70rpx;
		}
      }
      .pos_14 {
        position: absolute;
        right: 270rpx;
        top: 663rpx;
      }
      .section_4 {
        background-color: #e0e0e0;
        border-radius: 50%;
        width: 68rpx;
        height: 64rpx;
		overflow: hidden;
		image{
		  width: 68rpx;
		  height: 64rpx;
		}
      }
      .pos_7 {
        position: absolute;
        left: 108rpx;
        top: 283rpx;
      }
      .section {
        background-color: #e0e0e0;
        border-radius: 50%;
        width: 116rpx;
        height: 118rpx;
		overflow: hidden;
		image{
			width: 116rpx;
			height: 118rpx;
		}
      }
      .pos_2 {
        position: absolute;
        left: 66rpx;
        top: 41rpx;
		animation: floating1 2s infinite ease-in-out;
      }
      .section_11 {
        background-color: #e0e0e0;
        border-radius: 50%;
        width: 136rpx;
        height: 136rpx;
		overflow: hidden;
		image{
			width: 136rpx;
			height: 136rpx;
		}
      }
      .pos_15 {
        position: absolute;
        right: 82rpx;
        top: 713rpx;
		animation: floating1 2s infinite ease-in-out;
      }
      .section_8 {
        background-color: #e0e0e0;
        border-radius: 50%;
        width: 102rpx;
        height: 98rpx;
		overflow: hidden;
		image{
		  width: 102rpx;
		  height: 98rpx;
		}
      }
      .pos_12 {
        position: absolute;
        right: 168rpx;
        top: 545rpx;
      }
      .section_7 {
        background-color: #e0e0e0;
        border-radius: 50%;
        width: 60rpx;
        height: 60rpx;
		overflow: hidden;
		image{
			width: 60rpx;
			height: 60rpx;
		}
      }
      .pos_11 {
        position: absolute;
        right: 148rpx;
        top: 465rpx;
		animation: floating 2s infinite ease-in-out;
      }
      .section_5 {
        background-color: #e0e0e0;
        border-radius: 50%;
        width: 104rpx;
        height: 106rpx;
		overflow: hidden;
		image{
		  width: 104rpx;
		  height: 106rpx;
		}
      }
      .pos_9 {
        position: absolute;
        left: 168rpx;
        top: 345rpx;
      }
      .image_3 {
        width: 458rpx;
        height: 210rpx;
      }
      .pos_8 {
        position: absolute;
        left: 50%;
        bottom: 314rpx;
        transform: translateX(-50%);
      }
      .image_2 {
        border-radius: 50%;
        width: 616rpx;
        height: 386rpx;
      }
      .pos_5 {
        position: absolute;
        left: 50%;
        bottom: 224rpx;
        transform: translateX(-50%);
      }
      .image {
        width: 792rpx;
        height: 618rpx;
      }
      .pos_3 {
        position: absolute;
        left: -16rpx;
        right: -26rpx;
        bottom: 105rpx;
      }
      // .text-wrapper {
      //   padding: 56rpx 0 776rpx;
      //   background-image: url('https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385901956251944.png');
      //   background-size: 100% 100%;
      //   background-repeat: no-repeat;
      //   .text {
      //     margin-right: 108rpx;
      //     color: #ffffff;
      //     font-size: 36rpx;
      //     font-family: SegoeUI;
      //     line-height: 33rpx;
      //     text-shadow: 0px 6rpx 12rpx #00000029;
      //   }
      // }
      // .pos {
      //   position: absolute;
      //   left: -78rpx;
      //   right: -52rpx;
      //   top: 0;
      // }
	  
    }
	
	.text_2 {
	  //padding: 28rpx 0;
      //background-color: #ffffff;
      //border-radius: 60rpx;
      //width: 230rpx;
        color: #ffffff;
        font-size: 42rpx;
        //font-family: SegoeUI;
        line-height: 40rpx;
		font-weight: 700;
      }
    .text-wrapper_2 {//开始聊天
		background-color: #fff;
		padding: 25rpx 50rpx;
		border-radius: 30rpx;
		text{
			color: #362e45;
			font-size: 50rpx;
			font-weight: 700;
		}
    }
  }
  .space-y-48 {
    & > view:not(:first-child),
    & > text:not(:first-child),
    & > image:not(:first-child) {
      margin-top: 46rpx;
    }
  }
  
	  .load_14 {
	    display: inline-block;
	    width: 70px;
	    text-align: center;
	  }
	  .load_14 > view {
	    width: 18px;
	    height: 18px;
	    background-color: #FFFFFF;
	    border-radius: 100%;
	    display: inline-block;
	    -webkit-animation: sk-bouncedelay 1.4s infinite ease-in-out both;
	    animation: sk-bouncedelay 1.4s infinite ease-in-out both;
	  }
	  .load_14 .bounce1 {
	    -webkit-animation-delay: -0.32s;
	    animation-delay: -0.32s;
	  }
	  .load_14 .bounce2 {
	    -webkit-animation-delay: -0.16s;
	    animation-delay: -0.16s;
	  }
	  @-webkit-keyframes sk-bouncedelay {
	    0%, 80%, 100% { -webkit-transform: scale(0) }
	    40% { -webkit-transform: scale(1.0) }
	  }
	  @keyframes sk-bouncedelay {
	    0%, 80%, 100% { 
	      -webkit-transform: scale(0);
	      transform: scale(0);
	    } 40% { 
	      -webkit-transform: scale(1.0);
	      transform: scale(1.0);
	    }
	  }
</style>