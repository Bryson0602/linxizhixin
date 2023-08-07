<template>
  <view class="flex-col page space-y-8">
    <view class="flex-col section space-y-24">
      <text class="self-center font_1 text">签到</text>
      <view class="flex-col">
        <view class="flex-row justify-between items-center group">
          <view class="flex-col justify-start items-center text-wrapper">
            <text class="font_1 text_2">每日一签</text>
          </view>
          <view class="flex-col justify-start items-center text-wrapper_2">
            <text class="font_2 text_3">签到规则</text>
          </view>
        </view>
        <view class="flex-col section_2 space-y-16">
          <view class="flex-row justify-between items-center group_2">
            <view class="group_3">
              <text class="font_3 text_4">已连续签到</text>
              <text class="text_5">{{ days }}</text>
              <text class="font_3 text_6">天</text>
            </view>
            <view class="flex-col justify-start items-center text-wrapper_3">
              <text class="font_2 text_7">补签</text>
            </view>
          </view>
          <view class="flex-col">
            <view class="flex-row space-x-6">
              <view class="flex-col items-center equal-division-item space-y-6">
                <image
                  class="image"
                  src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385878621156073.png"
                />
                <text class="font_2">+1</text>
              </view>
              <view class="flex-col items-center equal-division-item space-y-6">
                <image
                  class="image"
                  src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385878650036673.png"
                />
                <text class="font_2">+1</text>
              </view>
              <view class="flex-col justify-start items-center equal-division-item_2" :style="buttonStyle" @click="handleSign">
                <text class="font_4 text_8">奖品</text>
              </view>
			  <view v-if="showSuccess" class="success-dialog">
			    <text class="ziti">签到成功！</text>
			  </view>
              <view class="flex-col items-center equal-division-item_3 space-y-6">
                <image
                  class="image"
                  src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385878650036673.png"
                />
                <text class="font_2">+1</text>
              </view>
              <view class="flex-col items-center equal-division-item_3 space-y-6">
                <image
                  class="image"
                  src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385878650036673.png"
                />
                <text class="font_2">+1</text>
              </view>
              <view class="flex-col items-center equal-division-item_3 space-y-4">
                <image
                  class="image"
                  src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385878650036673.png"
                />
                <text class="font_2">+2</text>
              </view>
              <view class="flex-col justify-start items-center equal-division-item_2">
                <text class="font_4 text_8">奖品</text>
              </view>
            </view>
            <view class="flex-row justify-between group_4" >
              <text class="font_5">第一天</text>
              <text class="font_5">第二天</text>
              <text class="font_5">第三天</text>
              <text class="font_5">第四天</text>
              <text class="font_5">第五天</text>
              <text class="font_5">第六天</text>
              <text class="font_5">第七天</text>
            </view>
            <text class="self-end font_4 text_9">获取更多小心心</text>
          </view>
        </view>
        <view class="flex-row equal-division space-x-11">
          <view class="flex-row justify-center items-center equal-division-item_4 space-x-12">
            <image
              class="image_2"
              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385877076566446.png"
            />
            <text class="font_6 text_10">小心心商城</text>
          </view>
          <view class="flex-row justify-center items-center equal-division-item_5 space-x-12">
            <image
              class="image_2"
              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385877286485015.png"
            />
            <text class="font_6">小心心活动</text>
          </view>
        </view>
      </view>
    </view>
    <view class="flex-col section_3 space-y-12">
      <text class="self-start font_7">小犀活动</text>
      <view class="flex-row space-x-15">
        <view class="section_4">
			<image class="daxiao1"  src="../../static/qiandao2 - 1.png" mode=""></image>
		</view>
        <view class="flex-col group_5 space-y-17">
          <view class="section_5">
			  <image class="daxiao2"  src="../../static/qiandao3.png" mode=""></image>
		  </view>
          <view class="section_5">
			  <image class="daxiao2" src="../../static/qiandao4-2.png" mode=""></image>
		  </view>
        </view>
      </view>
      <text class="self-start font_7 text_11">今日热门</text>
      <view class="flex-row space-x-15">
        <view class="section_6">
			<image class="daxiao3" src="../../static/qiandao5.png" mode=""></image>
		</view>
        <view class="section_6">
			<image class="daxiao3" src="../../static/qiandao6.png" mode=""></image>
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
		  days: 2, // 初始签到天数为0
		  isSigned: false, // 是否已签到的状态
		  showSuccess: false, // 是否显示签到成功提示框
	  };
    },
	computed: {
	  buttonStyle() {
	    return {
	      backgroundColor: this.isSigned ? '#65cbc8' : 'white',
	    };
	  },
	},
    methods: {
		handleSign() {
		  if (!this.isSigned) { // 如果未签到
		    this.days++; // 增加1天
		    this.isSigned = true; // 设置为已签到状态
		    this.showSuccess = true; // 显示签到成功提示框
		
		    setTimeout(() => { // 1秒后隐藏签到成功提示框
		      this.showSuccess = false;
		    }, 1000);
		  }
		},
	},
  };
</script>

<style scoped lang="scss">
	.success-dialog {
	  position: fixed;
	  top: 50%;
	  left: 50%;
	  transform: translate(-50%, -50%);
	  background: linear-gradient(
	         to bottom right, 
	         #eafbff 0%,
	         #edfbff 20%,
	         #edfbfe 40%,
	         #e8f8fe 60%,
	         #eaf1fb 80%,
	         #e8e6fb 100%
	       );
	  padding: 16px;
	  border-radius: 8px;
	  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
	}
  .page {
    background-color: #efefef;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .section {
      padding: 32rpx 0 32rpx 40rpx;
      background-color: #ffffff;
      .font_1 {
        font-size: 40rpx;
        font-family: SegoeUI-Bold;
        line-height: 37rpx;
        font-weight: 700;
      }
      .text {
        color: #1e1c1c;
        line-height: 36rpx;
      }
      .group {
        padding-bottom: 28rpx;
        .text-wrapper {
          padding: 24rpx 0;
          background-color: #96a1f9;
          border-radius: 60rpx;
          width: 210rpx;
          height: 82rpx;
          .text_2 {
            color: #ffffff;
          }
        }
        .text-wrapper_2 {
          padding: 16rpx 0;
          background-color: #efefef;
          border-radius: 60rpx 0 0 60rpx;
          width: 148rpx;
          height: 62rpx;
          .text_3 {
            color: #78708c;
            line-height: 26rpx;
          }
        }
      }
      .section_2 {
        margin-right: 40rpx;
        padding: 28rpx 26rpx;
        background-color: #b8eeec;
        border-radius: 24rpx;
        .group_2 {
          padding: 0 8rpx;
          .group_3 {
            line-height: 37rpx;
            height: 37rpx;
            .font_3 {
              font-size: 40rpx;
              font-family: SegoeUI;
              color: #1e1c1c;
            }
            .text_4 {
              line-height: 37rpx;
            }
            .text_5 {
              color: #1e1c1c;
              font-size: 40rpx;
              font-family: SegoeUI-Bold;
              font-weight: 700;
              line-height: 29rpx;
            }
            .text_6 {
              line-height: 34rpx;
            }
          }
          .text-wrapper_3 {
            margin-right: 8rpx;
            padding: 16rpx 0;
            background-color: #ffffff;
            border-radius: 60rpx;
            box-shadow: 0px 6rpx 12rpx #00000029;
            width: 100rpx;
            height: 54rpx;
            .text_7 {
              font-size: 26rpx;
              line-height: 24rpx;
            }
          }
        }
        .space-x-6 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-left: 12rpx;
          }
          .equal-division-item {
            flex: 1 1 78rpx;
            padding: 28rpx 0 16rpx;
            background-color: #65cbc8;
            border-radius: 24rpx;
            height: 106rpx;
          }
          .space-y-6 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-top: 12rpx;
            }
          }
          .equal-division-item_2 {
            flex: 1 1 78rpx;
            padding: 68rpx 0 16rpx;
            background-color: #ffffff;
            border-radius: 24rpx;
            height: 106rpx;
            .text_8 {
              line-height: 22rpx;
            }
          }
          .equal-division-item_3 {
            flex: 1 1 78rpx;
            padding: 28rpx 0 16rpx;
            background-color: #ffffff;
            border-radius: 24rpx;
            height: 106rpx;
          }
          .image {
            width: 32rpx;
            height: 32rpx;
          }
          .space-y-4 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-top: 8rpx;
            }
          }
        }
        .group_4 {
          margin-top: 12rpx;
          padding-left: 16rpx;
          padding-right: 12rpx;
		  
          .font_5 {
            font-size: 16rpx;
            font-family: SegoeUI;
            line-height: 15rpx;
            color: #1e1c1c;
			margin-left: -10rpx;
			margin-right: -8rpx;
          }
        }
        .font_4 {
          font-size: 24rpx;
          font-family: SegoeUI-Bold;
          line-height: 20rpx;
          font-weight: 700;
          color: #1e1c1c;
        }
        .text_9 {
          margin-right: 36rpx;
          margin-top: 44rpx;
          color: #59a09e;
          line-height: 22rpx;
        }
      }
      .space-y-16 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 32rpx;
        }
      }
      .font_2 {
        font-size: 28rpx;
        font-family: SegoeUI-Bold;
        line-height: 20rpx;
        font-weight: 700;
        color: #1e1c1c;
      }
      .equal-division {
        margin-right: 40rpx;
        margin-top: 40rpx;
        .equal-division-item_4 {
          padding: 24rpx 28rpx 24rpx 58rpx;
          flex: 1 1 324rpx;
          background-image: linear-gradient(90deg, #ffffff 23.9%, #c5dbff 121.2%);
          border-radius: 24rpx;
          height: 96rpx;
          .text_10 {
            line-height: 30rpx;
          }
        }
        .space-x-12 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-left: 24rpx;
          }
        }
        .equal-division-item_5 {
          padding: 24rpx 36rpx 24rpx 50rpx;
          flex: 1 1 324rpx;
          background-image: linear-gradient(90.1deg, #ffffff 18.6%, #ffdada 100%);
          border-radius: 24rpx;
          height: 96rpx;
        }
        .image_2 {
          width: 50rpx;
          height: 50rpx;
        }
        .font_6 {
          font-size: 32rpx;
          font-family: SegoeUI-Bold;
          line-height: 29rpx;
          font-weight: 700;
          color: #78708c;
        }
      }
      .space-x-11 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 22rpx;
        }
      }
    }
    .space-y-24 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 48rpx;
      }
    }
    .section_3 {
      padding: 36rpx 40rpx 0;
      background-color: #ffffff;
      .font_7 {
        font-size: 44rpx;
        font-family: SegoeUI-Bold;
        line-height: 40rpx;
        font-weight: 700;
        color: #1e1c1c;
      }
      .space-x-15 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 30rpx;
        }
        .section_4 {
          flex: 1 1 320rpx;
          background-color: #e7e7e7;
          border-radius: 24rpx;
          width: 320rpx;
          height: 352rpx;
		  position: relative;
		  .daxiao1{
			  width: 100%;
			  height: 100%;
			  object-fit: contain;
			  border-radius: 24rpx;
		  }
        }
        .group_5 {
          flex: 1 1 320rpx;
          .section_5 {
            background-color: #e7e7e7;
            border-radius: 24rpx;
            height: 160rpx;
			position: relative;
			.daxiao2{
				    width: 100%;
				    height: 100%;
				    object-fit: contain;
					border-radius: 24rpx;
			}
          }
        }
        .space-y-17 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 34rpx;
          }
        }
        .section_6 {
          flex: 1 1 320rpx;
          background-color: #e7e7e7;
          border-radius: 24rpx 24rpx 0 0;
          width: 320rpx;
          height: 338rpx;
		  position: relative;
		  .daxiao3{
			  width: 100%;
			  height: 100%;
			  object-fit: contain;
			  border-radius: 24rpx 24rpx 0 0;
		  }
        }
      }
      .text_11 {
        line-height: 41rpx;
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
  .space-y-8 {
    & > view:not(:first-child),
    & > text:not(:first-child),
    & > image:not(:first-child) {
      margin-top: 16rpx;
    }
  }
</style>