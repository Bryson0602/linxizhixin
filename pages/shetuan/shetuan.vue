<template>
  <view class="flex-col page space-y-18">
    <!-- <text class="self-center font_1 text">社团</text> -->
    <view class="flex-col space-y-16">
      <view class="flex-row justify-between items-end">
        <view class="flex-col justify-start items-center text-wrapper">
          <text class="font_2 text_2">推荐群组</text>
        </view>
        <view class="flex-row items-center space-x-4">
          <text class="font_2 text_3">全部</text>
          <image
            class="shrink-0 image"
            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385886079491941.png"
          />
        </view>
      </view>
      <view class="flex-col space-y-16">
		  
        <view class="flex-row items-center list-item space-x-14">
          <!-- <view class="shrink-0 section"> -->
			  <image src="../../static/kuakua.png" mode="" class="shrink-0 section"></image>
		  <!-- </view> -->
          <view class="flex-col flex-auto">
            <text class="self-start font_1">相互夸夸俱乐部</text>
            <text class="font_3 text_4">这里是一个夸夸群，无论做了任何</text>
            <text class="font_3 text_5">小事都值得被夸夸，欢迎大家加入</text>
            <view class="flex-row justify-between group">
              <text class="self-start font_3">噢~</text>
              <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_4">加入</text></view>
            </view>
          </view>
        </view>
		
		<view class="flex-row items-center list-item space-x-14">
		  <view class="shrink-0 section">
			  <image src="../../static/jinbu.png" mode="" class="shrink-0 section"></image>
		  </view>
		  <view class="flex-col flex-auto">
		    <text class="self-start font_1">积极进步俱乐部</text>
		    <text class="font_3 text_4">这里是一个积极进步的群体，无论你取得了什么小进步，我们都会给予夸奖和鼓励。</text>
		    <view class="flex-row justify-between group">
		      <text class="self-start font_3"></text>
		      <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_4">加入</text></view>
		    </view>
		  </view>
		</view>
		
		<view class="flex-row items-center list-item space-x-14">
		  <view class="shrink-0 section">
			   <image src="../../static/bangzhu.png" mode="" class="shrink-0 section"></image>
		  </view>
		  <view class="flex-col flex-auto">
		    <text class="self-start font_1">乐于助人俱乐部</text>
		    <text class="font_3 text_4">这里是一个乐于助人的群体，无论你为他人做了任何小事，我们都会给予感激和赞美。</text>
		    
		    <view class="flex-row justify-between group">
		      <text class="self-start font_3"></text>
		      <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_4">加入</text></view>
		    </view>
		  </view>
		</view>
		
		<view class="flex-row items-center list-item space-x-14">
		  <view class="shrink-0 section">
			  <image src="../../static/yonggan.png" mode="" class="shrink-0 section"></image>
		  </view>
		  <view class="flex-col flex-auto">
		    <text class="self-start font_1">勇敢挑战俱乐部</text>
		    <text class="font_3 text_4">这里是一个勇敢挑战的群体，无论你面对了什么困难和挑战，我们都会给予勇气和赞美。</text>
		    
		    <view class="flex-row justify-between group">
		      <text class="self-start font_3"></text>
		      <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_4">加入</text></view>
		    </view>
		  </view>
		</view>
		
		<view class="flex-row items-center list-item space-x-14">
		  <view class="shrink-0 section">
			  <image src="../../static/ganen.png" mode="" class="shrink-0 section"></image>
		  </view>
		  <view class="flex-col flex-auto">
		    <text class="self-start font_1">感恩幸福俱乐部</text>
		    <text class="font_3 text_4">这里是一个感恩幸福的群体，无论你经历了什么幸福时刻，我们都会给予祝福和庆祝。</text>
		    
		    <view class="flex-row justify-between group">
		      <text class="self-start font_3"></text>
		      <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_4">加入</text></view>
		    </view>
		  </view>
		</view>
		
      </view>
    </view>
  </view>
</template>

<script>
  export default {
    components: {},
    data() {
      return {
        list_dzUW41mr: [null, null, null, null, null],
      };
    },

    methods: {},
  };
</script>

<style scoped lang="scss">
  .page {
    padding: 36rpx 40rpx 20rpx;
    // background-color: #edeff1;
	background-image: linear-gradient(180deg, #ccf0f0 0%, #eff0ff 21.4%, #ffffff 48.5%, #eff0ff 76.7%, #ccf0f0 100%);
	// background-image: linear-gradient(180deg, #bdf5f0 0%, #f2f2e8 26.4%, #e8f5f4 51.1%, #59d5d3 100%);
	// background-image: radial-gradient(at center,rgb(141, 237, 251) 10%,rgb(111,201,253) 26.4%,rgb(94,186,253) 51.1%, rgb(79,171,254) 100%);
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .font_1 {
      font-size: 38rpx;
      font-family: SegoeUI-Bold;
      line-height: 35rpx;
      font-weight: 700;
      color: #202020;
    }
    .text {
      font-size: 40rpx;
      line-height: 37rpx;
    }
    .space-y-16 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 32rpx;
      }
      .text-wrapper {
        padding: 24rpx 0;
        background-color: #ffffff;
        border-radius: 40rpx;
        width: 178rpx;
        height: 74rpx;
        .text_2 {
          color: #78708c;
          font-size: 32rpx;
          line-height: 30rpx;
        }
      }
      .space-x-4 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 8rpx;
        }
        .text_3 {
          color: #707070;
          font-size: 32rpx;
          line-height: 30rpx;
        }
        .image {
          width: 36rpx;
          height: 36rpx;
        }
      }
      .font_2 {
        font-size: 30rpx;
        font-family: SegoeUI-Bold;
        line-height: 32rpx;
        font-weight: 700;
      }
      .list-item {
        padding: 28rpx;
        background-color: #ffffff;
        border-radius: 60rpx;
        .section {
			background-color: #fff;
          // background-color: #edeff1;
		  // background-image: url(../../);
          border-radius: 40rpx;
          width: 192rpx;
          height: 194rpx;
        }
        .font_3 {
          font-size: 26rpx;
          font-family: SegoeUI-Bold;
          line-height: 32rpx;
          font-weight: 700;
          color: #acb9cd;
        }
        .text_4 {
          margin-top: 20rpx;
        }
        .text_5 {
          margin-top: 4rpx;
        }
        .group {
          margin-top: 4rpx;
          .text-wrapper_2 {
            margin-right: 8rpx;
            padding: 12rpx 0;
            background-color: #7bdddb;
            border-radius: 40rpx;
            width: 110rpx;
            height: 50rpx;
            .font_4 {
              font-size: 30rpx;
              font-family: SegoeUI-Bold;
              line-height: 27rpx;
              font-weight: 700;
              color: #ffffff;
            }
          }
        }
      }
      .space-x-14 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 28rpx;
        }
      }
    }
  }
  .space-y-18 {
    & > view:not(:first-child),
    & > text:not(:first-child),
    & > image:not(:first-child) {
      margin-top: 36rpx;
    }
  }
</style>