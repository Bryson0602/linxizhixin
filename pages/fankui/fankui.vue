<template>
  <view class="flex-col page space-y-13">
    <text class="self-start text">HI~，有什么可以帮您！</text>
    <text class="self-start font_1 text_2">小犀为您服务</text>
    <view class="flex-col space-y-4">
      <text class="self-start font_2 text_3">工作时间：</text>
      <view class="flex-row space-x-8">
        <text class="font_2 text_4">工作日8：30-11：30</text>
        <text class="font_2 text_5">13：00-17：30</text>
      </view>
    </view>
    <view class="flex-col space-y-14">
      <view class="flex-col justify-start section">
        <view class="flex-row equal-division space-x-6">
          <view class="flex-col items-center equal-division-item space-y-6">
            <image
              class="image"
              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/d74f06fb4e22b456e10bd31533a9c366.png"
            />
            <text class="font_1">在线客服</text>
          </view>
          <view class="flex-col items-center equal-division-item space-y-6">
            <image
              class="image"
              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/8b3e70b82ae2f24756c81bb308fdbbc2.png"
            />
            <text class="font_1">我的投诉</text>
          </view>
          <view class="flex-col items-center equal-division-item space-y-6">
            <image
              class="image"
              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385883040620959.png"
            />
            <text class="font_1">意见反馈</text>
          </view>
        </view>
      </view>
      <view class="flex-col section_2 space-y-30">
        <view class="flex-col items-start space-y-18">
          <text class="text_6">常见问题</text>
          <text class="font_3">软件卡顿</text>
        </view>
        <text class="self-start font_3">页面显示异常</text>
        <text class="self-start font_3">视频无法正常观看</text>
        <text class="self-start font_3">软件闪退</text>
        <text class="self-start font_3">活动无法签退</text>
        <text class="self-start font_3">匹配界面异常</text>
        <text class="self-start font_3">聊天卡顿</text>
      </view>
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
  .page {
	  position: fixed;
    padding: 60rpx 40rpx 228rpx;
    background: linear-gradient(
           to bottom right, 
           #eafbff 0%,
           #edfbff 20%,
           #edfbfe 40%,
           #e8f8fe 60%,
           #eaf1fb 80%,
           #e8e6fb 100%
         );
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .text {
      margin-left: 4rpx;
      color: #202020;
      font-size: 52rpx;
      font-family: SegoeUI-Bold;
      font-weight: 700;
      line-height: 49rpx;
    }
    .font_1 {
      font-size: 36rpx;
      font-family: SegoeUI-Bold;
      line-height: 33rpx;
      font-weight: 700;
      color: #78708c;
    }
    .text_2 {
      color: #202020;
	  margin-left: 1rpx;
    }
    .space-y-4 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 8rpx;
      }
      .font_2 {
        font-size: 26rpx;
        font-family: SegoeUI-Bold;
        line-height: 30rpx;
        font-weight: 700;
        color: #202020;
      }
      .text_3 {
        line-height: 28rpx;
      }
      .space-x-8 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 16rpx;
        }
        .text_4 {
          line-height: 28rpx;
		  // margin-left: 4rpx;
        }
        .text_5 {
          line-height: 28rpx;
		  // margin-left: 4rpx;
        }
      }
    }
    .space-y-14 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 28rpx;
      }
      .section {
        padding: 20rpx 0 28rpx;
        filter: drop-shadow(0px 6rpx 6rpx #00000029);
        background-image: url('https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385881596231051.png');
        background-size: 100% 100%;
        background-repeat: no-repeat;
        .equal-division {
          padding: 0 12rpx;
          .equal-division-item {
            flex: 1 1 215rpx;
            padding: 8rpx 0;
            .image {
              width: 128rpx;
              height: 128rpx;
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
        .space-x-6 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-left: 12rpx;
          }
        }
      }
      .section_2 {
        padding: 44rpx 36rpx 64rpx;
        background-image: linear-gradient(180deg, #ffffff 0%, #ffffff 100%);
        border-radius: 24rpx;
        box-shadow: 6rpx 6rpx 12rpx #00000029;
        .space-y-18 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 36rpx;
          }
          .text_6 {
            color: #595959;
            font-size: 40rpx;
            font-family: SegoeUI-Bold;
            font-weight: 700;
            line-height: 37rpx;
          }
        }
        .font_3 {
          font-size: 32rpx;
          font-family: SegoeUI-Bold;
          line-height: 30rpx;
          font-weight: 700;
          color: #595959;
        }
      }
      .space-y-30 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 60rpx;
        }
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
</style>