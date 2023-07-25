<template>
	<view class="flex-col page">
	  <view class="flex-col flex-auto group">
	    <view class="flex-col space-y-15">
	      <view class="flex-col section_2">
	        <view class="flex-col items-center space-y-6">
	          <text class="text_2">SDS抑郁自评测试</text>
	          <text class="text_3">SDS Depression self-assessment test</text>
	        </view>
	        <view class="flex-row items-center group_2 space-x-9">
	          <view class="section_3"></view>
	          <text class="font_2">请在十分钟内完成</text>
	        </view>
	        <view class="flex-row items-center group_3 space-x-8">
	          <view class="section_3"></view>
	          <text class="font_2">诚实回答每个问题</text>
	        </view>
	        <view class="flex-row items-center group_4 space-x-8">
	          <view class="section_3"></view>
	          <text class="font_2">尽量不选择中立答案</text>
	        </view>
	      </view>
	      <view class="flex-col justify-start items-start self-center section_4"><view class="section_5"></view></view>
	    </view>
	    <view class="flex-row justify-between group_5">
	      <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_1 text_4">1</text></view>
	      <view class="flex-row section_6 space-x-10">
	        <image
	          class="shrink-0 self-center image"
	          src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901701522478464885.png"
	        />
	        <text class="self-start text_5">00：05</text>
	      </view>
	    </view>
	    <text class="self-center text_6">最近的一周内我有便秘的苦恼</text>
	    <view class="flex-col group_6 space-y-23">
	      <view class="flex-col space-y-23">
	        <view class="flex-col justify-start items-start text-wrapper_3 bianse"><text class="font_3 text_7">符合</text></view>
	        <view class="flex-col justify-start items-start text-wrapper_3">
	          <text class="font_3 text_7">有点符合</text>
	        </view>
	      </view>
	      <view class="flex-col space-y-23">
	        <view class="flex-col justify-start items-start text-wrapper_3">
	          <text class="font_3 text_7">不太符合</text>
	        </view>
	        <view class="flex-col justify-start items-start text-wrapper_3">
	          <text class="font_3 text_7">不符合</text>
	        </view>
	      </view>
	    </view>
	    <view class="flex-col justify-start items-center self-center button"><text class="text_8">上一题</text></view>
	  </view>
	</view>
</template>

<script>
  export default {
    components: {},
    data() {
      return {};
    },

    methods: {},
  };
</script>

<style scoped lang="scss">
.bianse text:hover {
				-webkit-filter: grayscale(100%); 
				-moz-filter: grayscale(100%); 
				-ms-filter: grayscale(100%); 
				-o-filter: grayscale(100%); 
				filter: grayscale(100%); 
				filter: gray;
			}
  .page {
	  position: fixed;
    background-color: #f5f5f5;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .group {
      padding-bottom: 58rpx;
      overflow-y: auto;
      .space-y-15 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 30rpx;
        }
        .section_2 {
          padding: 72rpx 68rpx 40rpx 74rpx;
          background-color: #6453ce;
          box-shadow: 0px 6rpx 16rpx #a5a5a529;
          .space-y-6 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-top: 12rpx;
            }
            .text_2 {
              color: #ffffff;
              font-size: 56rpx;
              font-family: SegoeUI-Bold;
              font-weight: 700;
              line-height: 52rpx;
            }
            .text_3 {
              color: #ffffff;
              font-size: 34rpx;
              font-family: SegoeUI;
              line-height: 33rpx;
            }
          }
          .group_2 {
            margin-top: 40rpx;
          }
          .space-x-9 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 18rpx;
            }
          }
          .group_3 {
            margin-top: 16rpx;
          }
          .space-x-8 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 16rpx;
            }
          }
          .section_3 {
            background-color: #d8d8d8;
            border-radius: 50%;
            width: 12rpx;
            height: 12rpx;
          }
          .font_2 {
            font-size: 24rpx;
            font-family: SegoeUI;
            line-height: 22rpx;
            color: #d8d8d8;
          }
          .group_4 {
            margin-top: 16rpx;
          }
        }
        .section_4 {
          background-color: #d8d8d8;
          border-radius: 24rpx;
          width: 608rpx;
          .section_5 {
            background-color: #6453ce;
            border-radius: 24rpx;
            width: 40rpx;
            height: 16rpx;
          }
        }
      }
      .group_5 {
        margin-top: 58rpx;
        padding: 0 56rpx;
        .text-wrapper_2 {
          padding: 20rpx 0 16rpx;
          background-color: #6453ce;
          border-radius: 50%;
          width: 72rpx;
          height: 72rpx;
          .font_1 {
            font-size: 48rpx;
            font-family: SegoeUI-Bold;
            font-weight: 700;
          }
          .text_4 {
            color: #ffffff;
            line-height: 34rpx;
          }
        }
        .section_6 {
          padding: 10rpx 24rpx;
          background-color: #ffffff;
          border-radius: 32rpx;
          box-shadow: 0px 6rpx 16rpx #a5a5a529;
          height: 68rpx;
          .image {
            width: 48rpx;
            height: 48rpx;
          }
          .text_5 {
            margin-top: 13rpx;
            color: #707070;
            font-size: 36rpx;
            font-family: SegoeUI-Bold;
            font-weight: 700;
            line-height: 26rpx;
          }
        }
        .space-x-10 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-left: 20rpx;
          }
        }
      }
      .text_6 {
        margin-top: 68rpx;
        color: #202020;
        font-size: 44rpx;
        font-family: SegoeUI-Bold;
        font-weight: 700;
        line-height: 41rpx;
      }
      .group_6 {
        margin-top: 108rpx;
        padding: 0 40rpx;
      }
      .space-y-23 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 46rpx;
        }
        .text-wrapper_3 {
          padding: 32rpx 0;
          background-color: #ffffff;
          border-radius: 24rpx;
          box-shadow: 0px 6rpx 12rpx #9b9b9b29;
          .font_3 {
            font-size: 40rpx;
            font-family: SegoeUI-Bold;
            line-height: 37rpx;
            font-weight: 700;
            color: #202020;
          }
          .text_7 {
            margin-left: 52rpx;
          }
        }
      }
      .button {
        margin-top: 70rpx;
        padding: 32rpx 0 32rpx;
        background-color: #6453ce;
        border-radius: 32rpx;
        box-shadow: 0px 6rpx 16rpx #a5a5a529;
        width: 336rpx;
        .text_8 {
          color: #ffffff;
          font-size: 52rpx;
          font-family: SegoeUI-Bold;
          font-weight: 700;
          line-height: 47rpx;
        }
      }
    }
  }
</style>