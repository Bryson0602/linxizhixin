<template>
	<view class="flex-col page">
	  <view class="flex-col section space-y-22">
	    <text class="self-center font_1 text">话题</text>
	    <view class="flex-col justify-start items-center text-wrapper">
	      <text class="font_b text_2">热门话题·每日更新</text>
	    </view>
	  </view>
	  <view class="flex-col group space-y-6">
	    <view class="flex-row justify-between">
	      <text class="font_2 text_3">我的</text>
	      <text class="font_2">热搜</text>
	      <text class="font_2 text_4">娱乐</text>
	      <text class="font_2">校园</text>
	      <text class="font_2">更多</text>
	    </view>
	    <image
	      class="self-start image"
	      src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385880085263447.png"
	    />
	  </view>
	  <!-- <view class="self-start section_2"></view> -->
	  <view class="flex-col list space-y-8">
	    <view class="flex-row justify-between items-center list-item" :key="i" v-for="(item, i) in list_yYZhF3Yo" :class="{'color-red': i < 5}">
	       <view class="flex-row items-baseline space-x-22">
	        <text class="font_3 text_5">{{i+1}}</text>
	        <text class="font_1 text_6">{{item}}</text>
	      </view>
	      <image
	        class="image_2"
	        src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385880116684411.png" v-if="i<3"
	      />
	    </view>
	  </view>
	  
	</view>
</template>

<script>
  export default {
    components: {},
    data() {
      return {
        list_yYZhF3Yo: ["什么是阳光抑郁症？", "解压小妙招", "抑郁症早期表现", "拒绝自我内耗", "双向情感障碍", "心理健康的重要性", "焦虑症的综合治疗", "寝室纠纷如何完美化解", "如何处理人际关系冲突", "如何在工作中促进心理健康", "讨论儿童的认知、情感","了解睡眠对心理健康的重要性"],
      };
    },

    methods: {},
  };
</script>

<style scoped lang="scss">
.color-red {
  color: gold; /* 设置需要修改的颜色，这里设为红色 */
}
  .page {
	  position: fixed;
    padding-bottom: 52rpx;
    background-color: #edf2f7;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .section {
      padding: 40rpx 166rpx 32rpx;
      background: linear-gradient(
             to bottom right, 
             #eafbff 0%,
             #edfbff 20%,
             #edfbfe 40%,
             #e8f8fe 60%,
             #eaf1fb 80%,
             #e8e6fb 100%
           );
      .text {
        color: #1e1c1c;
      }
      .text-wrapper {
        padding: 28rpx 0;
        background-color: #cdecec;
        border-radius: 60rpx;
		width: 450rpx;
        .text_2 {
          color: #555;
		  margin-left: 15rpx;
        }
      }
    }
    .space-y-22 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 44rpx;
      }
    }
    .group {
      padding: 28rpx 40rpx 8rpx;
      .font_2 {
        font-size: 32rpx;
        font-family: SegoeUI-Bold;
        line-height: 30rpx;
        font-weight: 700;
        color: #acb9cd;
      }
      .text_3 {
        color: #78708c;
      }
      .text_4 {
        line-height: 29rpx;
      }
      .image {
        width: 64rpx;
        height: 6rpx;
      }
    }
    .space-y-6 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 12rpx;
      }
    }
    .section_2 {
      margin-left: -40rpx;
      background-color: #cdecec;
      width: 830rpx;
      height: 20rpx;
    }
    .list {
      padding: 8rpx 40rpx;
      .list-item {
        padding: 16rpx 28rpx;
        background-color: #ffffff;
        border-radius: 60rpx;
        .space-x-22 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-left: 44rpx;
          }
          .font_3 {
            font-size: 48rpx;
            font-family: SegoeUI-Bold;
            line-height: 34rpx;
            font-weight: 700;
            color: #a9a9a9;
          }
          .text_5 {
            color: #ffb332;
          }
          .text_6 {
            color: #59a09e;
          }
        }
        .image_2 {
          width: 56rpx;
          height: 56rpx;
        }
      }
    }
    .space-y-8 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 16rpx;
      }
    }
    .font_1 {
      font-size: 40rpx;
      font-family: SegoeUI-Bold;
      line-height: 37rpx;
      font-weight: 700;
      color: #898989;
	  
    }
	.font_a {
		font-size: 40rpx;
		font-family: SegoeUI-Bold;
		line-height: 37rpx;
		font-weight: 700;
		color: #000000;
	}
	.font_b {
		font-size: 40rpx;
		font-family: SegoeUI-Bold;
		line-height: 37rpx;
		font-weight: 700;
		color: #666;
		letter-spacing:6rpx;
	}
  }
</style>
