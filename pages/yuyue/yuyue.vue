<template>
	<view class="flex-col page">
	  <view class="flex-col section space-y-20">
	    <view class="flex-row justify-center items-center group space-x-22">
	      <view class="section_2"></view>
	      <view class="flex-col group_2 space-y-18">
	        <view class="flex-col space-y-12">
	          <view class="flex-row items-baseline group_3 space-x-14">
	            <text class="text">徐老师</text>
	            <text class="text_2">心理咨询师</text>
	          </view>
	          <view class="flex-row group_3 space-x-28">
	            <text class="font_1">清华大学</text>
	            <text class="font_1">心理学</text>
	          </view>
	        </view>
	        <text class="self-start font_1 text_3">擅长：抑郁症、焦虑症咨询</text>
	      </view>
	    </view>
	    <view class="flex-row equal-division space-x-8">
	      <view class="flex-col items-center equal-division-item space-y-6">
	        <text class="font_2">3000</text>
	        <text class="font_3">预约量</text>
	      </view>
	      <view class="flex-col items-center equal-division-item space-y-6">
	        <text class="font_2">3000</text>
	        <text class="font_3">咨询量</text>
	      </view>
	      <view class="flex-col items-center equal-division-item space-y-6">
	        <text class="font_2">3000</text>
	        <text class="font_3">关注量</text>
	      </view>
	    </view>
	  </view>
	  <view class="flex-row justify-evenly items-center self-center section_3">
	    <view class="flex-col justify-start"><text class="font_4 text_4">预约挂号</text></view>
	    <view class="flex-col justify-start"><text class="font_5 text_5">患者评价</text></view>
	    <view class="flex-col justify-start"><text class="font_5 text_6">问诊历史</text></view>
	  </view>
	  <view class="flex-col section_4 space-y-36">
	    <view class="flex-row relative">
	      <view class="flex-col justify-start items-center text-wrapper"><text class="font_4">约满</text></view>
	      <view class="flex-col justify-start items-center text-wrapper view"><text class="font_4">约满</text></view>
	      <view class="flex-row shrink-0 group_4 space-x-30 pos">
	        <view class="flex-col items-center section_5 space-y-18">
	          <text class="font_6">07/08</text>
	          <text class="font_7">周六上午</text>
	        </view>
	        <view class="flex-col items-center section_5 space-y-18">
	          <text class="font_6">07/08</text>
	          <text class="font_7">周六下午</text>
	        </view>
	      </view>
	    </view>
	    <view class="flex-row relative">
	      <view class="flex-col justify-start items-center text-wrapper"><text class="font_4">约满</text></view>
	      <view class="flex-col justify-start items-center text-wrapper view_2"><text class="font_4">约满</text></view>
	      <view class="flex-row shrink-0 group_4 space-x-30 pos_2">
	        <view class="flex-col items-center section_5 space-y-18">
	          <text class="font_6">07/09</text>
	          <text class="font_7">周六上午</text>
	        </view>
	        <view class="flex-col items-center section_5 space-y-18">
	          <text class="font_6">07/09</text>
	          <text class="font_7">周六下午</text>
	        </view>
	      </view>
	    </view>
	    <view class="flex-row relative">
	      <view class="flex-col justify-start items-center text-wrapper"><text class="font_4">约满</text></view>
	      <view class="flex-col justify-start items-center text-wrapper view_3"><text class="font_4">约满</text></view>
	      <view class="flex-row shrink-0 group_4 space-x-30 pos_3">
	        <view class="flex-col items-center section_5 space-y-18">
	          <text class="font_6">07/10</text>
	          <text class="font_7">周六上午</text>
	        </view>
	        <view class="flex-col items-center section_5 space-y-18">
	          <text class="font_6">07/10</text>
	          <text class="font_7">周六下午</text>
	        </view>
	      </view>
	    </view>
	  </view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style scoped lang="scss">
.page {
    padding-bottom: 96rpx;
    background-color: #ffffff;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .section {
      padding: 55rpx 0 20rpx;
      background-color: #edf2f7;
      .group {
        padding: 0 68rpx;
        .section_2 {
          background-color: #ffffff;
          width: 170rpx;
          height: 170rpx;
        }
        .group_2 {
          width: 401rpx;
          .space-y-12 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-top: 24rpx;
            }
            .group_3 {
              padding: 0 4rpx;
              .text {
                color: #000000;
                font-size: 52rpx;
                font-family: SegoeUI-Bold;
                font-weight: 700;
                line-height: 48rpx;
              }
              .text_2 {
                color: #000000;
                font-size: 36rpx;
                font-family: SegoeUI-Bold;
                font-weight: 700;
                line-height: 33rpx;
              }
            }
            .space-x-14 {
              & > view:not(:first-child),
              & > text:not(:first-child),
              & > image:not(:first-child) {
                margin-left: 28rpx;
              }
            }
            .space-x-28 {
              & > view:not(:first-child),
              & > text:not(:first-child),
              & > image:not(:first-child) {
                margin-left: 56rpx;
              }
            }
          }
          .font_1 {
            font-size: 24rpx;
            font-family: SegoeUI;
            line-height: 22rpx;
            color: #000000;
          }
          .text_3 {
            margin-left: 4rpx;
          }
        }
      }
      .space-x-22 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 44rpx;
        }
      }
      .equal-division {
        padding: 0 16rpx;
        .equal-division-item {
          flex: 1 1 238rpx;
          padding: 8rpx 0;
          .font_2 {
            font-size: 24rpx;
            font-family: SegoeUI-Bold;
            line-height: 18rpx;
            font-weight: 700;
            color: #78708c;
          }
          .font_3 {
            font-size: 24rpx;
            font-family: SegoeUI-Bold;
            line-height: 22rpx;
            font-weight: 700;
            color: #78708c;
          }
        }
        .space-y-6 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 12rpx;
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
    }
    .space-y-20 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 40rpx;
      }
    }
    .section_3 {
      margin-top: 30rpx;
      padding: 28rpx 36rpx;
      background-color: #e8f5f4;
      border-radius: 60rpx;
      width: 614rpx;
      .text_4 {
        color: #202020;
      }
      .font_5 {
        font-size: 32rpx;
        font-family: SegoeUI-Bold;
        line-height: 31rpx;
        font-weight: 700;
        color: #707070;
      }
      .text_5 {
        margin: 0 16rpx;
        line-height: 30rpx;
      }
      .text_6 {
        margin: 0 16rpx;
        line-height: 30rpx;
      }
    }
    .section_4 {
      margin: 24rpx 40rpx 0;
      padding: 36rpx 56rpx 48rpx;
      background-color: #e8f5f4;
      border-radius: 60rpx;
      .text-wrapper {
        flex: 1 1 248rpx;
        padding: 192rpx 0 20rpx;
        background-color: #65cbc8;
        border-radius: 60rpx;
        height: 248rpx;
      }
      .view {
        margin-left: 60rpx;
      }
      .group_4 {
        overflow: hidden;
        height: 180rpx;
        .section_5 {
          margin-bottom: -68rpx;
          flex: 1 1 248rpx;
          padding: 40rpx 0 104rpx;
          background-color: #ffffff;
          border-radius: 60rpx;
          height: 248rpx;
          .font_6 {
            font-size: 40rpx;
            font-family: SegoeUI-Bold;
            line-height: 31rpx;
            font-weight: 700;
            color: #202020;
          }
          .font_7 {
            font-size: 40rpx;
            font-family: SegoeUI-Bold;
            line-height: 37rpx;
            font-weight: 700;
            color: #707070;
          }
        }
      }
      .space-x-30 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 60rpx;
        }
      }
      .pos {
        position: absolute;
        left: 0;
        right: 0;
        top: 0;
      }
      .view_2 {
        margin-left: 60rpx;
      }
      .pos_2 {
        position: absolute;
        left: 0;
        right: 0;
        top: 0;
      }
      .view_3 {
        margin-left: 60rpx;
      }
      .pos_3 {
        position: absolute;
        left: 0;
        right: 0;
        top: 0;
      }
    }
    .space-y-36 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 72rpx;
      }
    }
    .font_4 {
      font-size: 40rpx;
      font-family: SegoeUI-Bold;
      line-height: 37rpx;
      font-weight: 700;
      color: #ffffff;
    }
    .space-y-18 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 36rpx;
      }
    }
  }
</style>
