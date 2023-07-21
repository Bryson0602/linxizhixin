<template>
  <view class="flex-col page space-y-10">
	  <uni-calendar 
	  	:insert="true"
	  	:lunar="true" 
	  	:start-date="'2022-3-2'"
	  	:end-date="'2024-5-20'"
		:showMonth="false"
	  	@change="change"
	  	 />
    
    <view class="flex-col section_2 space-y-28">
      <view class="flex-col items-start group_5 space-y-6">
        <text class="font_1 text_19">我的活动</text>
        <view class="section_3"></view>
      </view>
      <!-- <view class="self-center section_4"></view> -->
      <!-- <text class="self-center text_20">今日没有报名的活动哦</text> -->
	  <view class="flex-col list space-y-10">
	    <view class="flex-col items-start relative list-item" :key="i" v-for="(item, i) in list_RiXSrhKo" @click="gohuodong">
	      <text class="font_6">心理疾病知识大讲堂</text>
	      <text class="font_8 text_25">2023.07.08-2023.07.10</text>
	      <view class="flex-col justify-start items-center text-wrapper_3 pos"><text class="font_7">进行中</text></view>
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
	      list_RiXSrhKo: [null, null, null],
	    };
	  },
	  methods: {
		gohuodong(){
			uni.navigateTo({
				url:'/pages/huodong/huodong'
			})
		}
	  },
	};
</script>

<style scoped lang="scss">
  .page {
    background-color: #ebebeb;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .section_2 {
      padding: 0 40rpx 316rpx;
      background-color: #ffffff;
	  
	  .list {
	    //padding: 30rpx 40rpx 20rpx;
	    .list-item {
	      padding: 32rpx 24rpx 32rpx;
	      background-color: #e6f3ff;
	      border-radius: 32rpx;
	      .font_8 {
	        font-size: 24rpx;
	        font-family: SegoeUI;
	        line-height: 28rpx;
	        color: #707070;
	      }
	      .text_25 {
	        margin-left: 8rpx;
	        margin-top: 40rpx;
	      }
	      .text-wrapper_3 {
	        padding: 8rpx 0;
	        background-color: #ffb276;
	        border-radius: 60rpx;
	        width: 118rpx;
	        .font_7 {
	          font-size: 24rpx;
	          font-family: SegoeUI-Bold;
	          line-height: 22rpx;
	          font-weight: 700;
	          color: #ffffff;
	        }
	      }
	      .pos {
	        position: absolute;
	        right: 16rpx;
	        top: 18rpx;
	      }
	    }
	  }
	  
      .group_5 {
        padding: 32rpx 0;
        .text_19 {
          color: #707070;
        }
        .section_3 {
          background-color: #65cbc8;
          border-radius: 60rpx;
          width: 192rpx;
          height: 8rpx;
        }
      }
      .space-y-6 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 12rpx;
        }
      }
      .section_4 {
        background-color: #b4b4b4;
        border-radius: 50%;
        width: 268rpx;
        height: 268rpx;
      }
      .text_20 {
        color: #707070;
        font-size: 40rpx;
        font-family: SegoeUI-Bold;
        font-weight: 700;
        line-height: 37rpx;
      }
    }
    .space-y-28 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        // margin-top: 56rpx;
      }
    }
    .font_1 {
      font-size: 48rpx;
      font-family: SegoeUI-Bold;
      line-height: 44rpx;
      font-weight: 700;
    }
  }
  .space-y-10 {
    & > view:not(:first-child),
    & > text:not(:first-child),
    & > image:not(:first-child) {
      margin-top: 20rpx;
    }
  }
</style>
