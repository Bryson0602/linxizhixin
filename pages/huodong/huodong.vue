<template>
	<view class="flex-col page">
	  <view class="flex-col section">
	    <!-- <view class="flex-col group">
	      <view class="flex-row items-center group_2">
	        <view class="flex-col justify-start"><text class="text">活动</text></view>
	        <view class="flex-col justify-start items-center text-wrapper view"><text class="font_1">学习</text></view>
	        <view class="flex-col justify-start items-center text-wrapper view_2"><text class="font_1">预约</text></view>
	      </view>
	      <view class="self-start section_2"></view>
	    </view> -->
	    <!-- <view class="flex-row justify-between items-center group_3">
	      <view class="flex-row items-baseline space-x-20">
	        <text class="text_2">报名</text>
	        <text class="font_2 text_3">部落</text>
	      </view>
	      <text class="font_2 text_4">活动日历</text>
	    </view> -->
	    <view class="flex-col group_4 space-y-24">
	      <view class="flex-row space-x-8">
	        <view class="flex-col justify-start items-end section_3">
				<image src="../../static/lb4.jpg" mode=""></image>
	          <view class="flex-col justify-start items-center text-wrapper_2"><text class="text_6">推荐</text></view>
	        </view>
	        <text class="self-start font_1 text_5">心理知识大讲堂</text>
	      </view>
	      <view class="flex-row justify-between items-baseline">
	        <view class="group_5">
	          <text class="font_2">可参与人数：</text>
	          <text class="text_7">20人</text>
	        </view>
	        <text class="font_2">已报名：18人</text>
	        <text class="font_2 text_8">已签到：6人</text>
	      </view>
	    </view>
	    <view class="flex-col group_6 space-y-12">
	      <view class="flex-row justify-between items-center">
	        <text class="font_3">报名时间</text>
	        <text class="font_4 text_9">2023.07.08-2023.07.10</text>
	      </view>
	      <view class="flex-row justify-between items-center">
	        <text class="font_3 text_10">活动时间</text>
	        <text class="font_4 text_11">2023.07.08-2023.07.10</text>
	      </view>
	    </view>
	  </view>
	  <view class="flex-col section_4">
	    <view class="flex-col justify-start items-start text-wrapper_3">
	      <text class="font_5 text_12">公告:暂无</text>
	    </view>
	    <view class="flex-col group_7 space-y-20">
	      <view class="flex-row justify-between items-center group_8">
	        <view class="flex-col justify-start"><text class="text_13">信息</text></view>
	        <view class="flex-col justify-start"><text class="font_6 text_14">详情</text></view>
	        <view class="flex-col justify-start"><text class="font_6 text_15">评价</text></view>
	      </view>
	      <view class="flex-col items-start section_5 space-y-20">
	        <text class="font_7">报名方式：审核制</text>
	        <text class="font_7">签到方式：外勤签到</text>
	        <text class="font_7">定位签到：不支持</text>
	        <text class="font_7">签退情况：无需签退</text>
	        <text class="font_7">活动分类：心理素质拓展</text>
	        <text class="font_7">活动对象：全体在校师生</text>
	        <text class="font_7">联系方式：灵犀知心</text>
	      </view>
	    </view>
	  </view>
	  <view class="flex-row justify-end section_6 space-x-8-reverse">
	    <view class="flex-col justify-start items-center text-wrapper_4"><text class="font_5">打卡结果</text></view>
	    <view class="flex-col justify-start items-center text-wrapper_5"><text class="font_5">报名</text></view>
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
	position: fixed;
    background-color: #ebebeb;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .section {
      padding: 40rpx 40rpx 16rpx;
      background-color: #ffffff;
      // .group {
      //   padding: 0 90rpx;
      //   .group_2 {
      //     padding: 0 4rpx 8rpx;
      //     .text {
      //       color: #202020;
      //       font-size: 52rpx;
      //       font-family: SegoeUI-Bold;
      //       font-weight: 700;
      //       line-height: 48rpx;
      //     }
      //     .text-wrapper {
      //       width: 104rpx;
      //     }
      //     .view {
      //       margin-left: 76rpx;
      //     }
      //     .view_2 {
      //       margin-left: 88rpx;
      //     }
      //   }
      //   .section_2 {
      //     background-color: #65cbc8;
      //     border-radius: 60rpx;
      //     width: 108rpx;
      //     height: 12rpx;
      //   }
      // }
      // .group_3 {
      //   margin-top: 44rpx;
      //   padding: 0 24rpx;
      //   .space-x-20 {
      //     & > view:not(:first-child),
      //     & > text:not(:first-child),
      //     & > image:not(:first-child) {
      //       margin-left: 40rpx;
      //     }
      //     .text_2 {
      //       color: #202020;
      //       font-size: 32rpx;
      //       font-family: SegoeUI-Bold;
      //       font-weight: 700;
      //       line-height: 30rpx;
      //     }
      //     .text_3 {
      //       color: #b4b4b4;
      //     }
      //   }
      //   .text_4 {
      //     margin-right: 48rpx;
      //   }
      // }
      .group_4 {
        margin-top: 0rpx;
        .space-x-8 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-left: 16rpx;
          }
          .section_3 {
			position: relative;
            //padding: 12rpx 0 102rpx;
            background-color: #707070;
            border-radius: 24rpx;
            width: 196rpx;
            height: 146rpx;
			overflow: hidden;
			
			image{
				width: 196rpx;
				height: 146rpx;
			}
            .text-wrapper_2 {
			  position: absolute;
			  right: 10rpx;
			  top: 10rpx;
              //margin-right: 14rpx;
              padding: 8rpx 0;
              background-color: #ff8323;
              border-radius: 60rpx;
              width: 68rpx;
              .text_6 {
                color: #ffffff;
                font-size: 20rpx;
                font-family: SegoeUI-Bold;
                font-weight: 700;
                line-height: 18rpx;
              }
            }
          }
          .text_5 {
            margin-top: 8rpx;
            color: #202020;
          }
        }
        .group_5 {
          line-height: 26rpx;
          height: 26rpx;
          .text_7 {
            color: #707070;
            font-size: 28rpx;
            font-family: SegoeUI;
            line-height: 26rpx;
          }
        }
        .text_8 {
          margin-right: 8rpx;
        }
      }
      .space-y-24 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 48rpx;
        }
      }
      .font_1 {
        font-size: 40rpx;
        font-family: SegoeUI-Bold;
        line-height: 37rpx;
        font-weight: 700;
        color: #707070;
      }
      .font_2 {
        font-size: 28rpx;
        font-family: SegoeUI-Bold;
        line-height: 26rpx;
        font-weight: 700;
        color: #707070;
      }
      .group_6 {
        margin-top: 60rpx;
        padding-left: 68rpx;
        padding-right: 64rpx;
        .font_3 {
          font-size: 32rpx;
          font-family: SegoeUI;
          line-height: 30rpx;
          color: #707070;
        }
        .font_4 {
          font-size: 32rpx;
          font-family: SegoeUI;
          line-height: 37rpx;
          color: #000000;
        }
        .text_9 {
          line-height: 38rpx;
        }
        .text_10 {
          line-height: 29rpx;
        }
        .text_11 {
          line-height: 38rpx;
        }
      }
      .space-y-12 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 24rpx;
        }
      }
    }
    .section_4 {
      margin-top: 20rpx;
      padding: 26rpx 40rpx 0;
      background-color: #ffffff;
      height: 100%;
      .text-wrapper_3 {
        padding: 36rpx 0;
        background-color: #e8f5f4;
        border-radius: 36rpx;
        .text_12 {
          margin-left: 36rpx;
		  line-height: 50rpx;
        }
      }
      .group_7 {
        margin: 40rpx 0 ;
        .group_8 {
          padding-left: 108rpx;
          padding-right: 96rpx;
          .text_13 {
            color: #000000;
            font-size: 44rpx;
            font-family: SegoeUI-Bold;
            font-weight: 700;
            line-height: 41rpx;
          }
          .font_6 {
            font-size: 36rpx;
            font-family: SegoeUI;
            line-height: 33rpx;
            color: #707070;
          }
          .text_14 {
            margin: 0 8rpx;
          }
          .text_15 {
            margin: 0 8rpx;
          }
        }
        .section_5 {
          padding: 40rpx 36rpx 64rpx;
          background-color: #f3f3f3;
          border-radius: 36rpx;
          .font_7 {
            font-size: 36rpx;
            font-family: SegoeUI;
            line-height: 44rpx;
            color: #707070;
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
    }
    .section_6 {
	  position: fixed;
	  width: 100%;
	  right: 0;
	  bottom: 0;
      padding: 20rpx 40rpx;
      background-color: #badff5;
      .text-wrapper_4 {
        padding: 24rpx 0;
        background-color: #ffffff;
        border-radius: 24rpx;
        width: 248rpx;
        height: 78rpx;
      }
      .text-wrapper_5 {
        padding: 24rpx 0;
        background-color: #ffffff;
        border-radius: 24rpx;
        width: 190rpx;
        height: 78rpx;
      }
    }
    .space-x-8-reverse {
      & > view:not(:last-child),
      & > text:not(:last-child),
      & > image:not(:last-child) {
        margin-right: 16rpx;
      }
    }
    .font_5 {
      font-size: 36rpx;
      font-family: SegoeUI-Bold;
      line-height: 33rpx;
      font-weight: 700;
      color: #000000;
    }
  }
</style>
