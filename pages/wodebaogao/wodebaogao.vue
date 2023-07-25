<template>
  <view class="flex-col page">
    <view class="flex-col flex-auto group">
      <view class="flex-col space-y-16">
        <text class="self-start font_1 text_2">数据分析</text>
        <view class="flex-col section">
          <view class="flex-row justify-center group_2 space-x-20">
            <view class="flex-col justify-start items-center text-wrapper">
              <text class="font_2 text_3">近7天</text>
            </view>
            <view class="flex-col justify-start items-center text-wrapper_2">
              <text class="font_2 text_4">近30天</text>
            </view>
          </view>
          <view class="flex-row justify-around group_3">
            <view class="flex-row space-x-20">
              <view class="flex-col items-center space-y-50">
                <text class="font_3">高</text>
                <text class="font_3">中</text>
                <text class="font_3">低</text>
                <text class="font_3 text_5">无</text>
              </view>
              <view class="self-start section_3"></view>
            </view>
            <view class="self-start section_4"></view>
            <view class="self-start section_5"></view>
            <view class="self-center section_2"></view>
            <view class="self-start section_6"></view>
          </view>
          <view class="flex-row justify-between group_4">
            <text class="font_3">抑郁</text>
            <text class="font_3">焦虑</text>
            <text class="font_3">燥怒</text>
            <text class="font_3">不安</text>
            <text class="font_3">恐惧</text>
          </view>
          <view class="flex-row justify-center group_5 space-x-12">
            <view class="section_7"></view>
            <view class="section_8"></view>
            <view class="section_8"></view>
            <view class="section_8"></view>
          </view>
        </view>
      </view>
      <view class="flex-col group_6 space-y-12">
        <text class="self-start font_1 text_6">历史报告</text>
        <view class="flex-col">
          <view class="flex-col justify-start items-start section_9">
            <view class="flex-row items-center section_10 space-x-12">
              <image
                class="image_2"
                src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901700541890096354.png"
              />
              <view class="flex-col items-start space-y-8">
                <text class="font_4">SDS抑郁自评测试</text>
                <text class="font_5 text_7">2023.7.9</text>
              </view>
			  <img class="tupian2" src="../../static/jiantou.png" alt="">
            </view>
          </view>
          <view class="flex-col justify-start items-start relative section_9 view">
            <view class="flex-row items-center section_10 space-x-12">
              <image
                class="image_2"
                src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901700541912876113.png"
              />
              <view class="flex-col items-start space-y-12">
                <text class="font_4">心理卫生评定测试</text>
                <text class="font_5 text_7">2023.6.15</text>
              </view>
			  <img class="tupian3" src="../../static/jiantou.png" alt="">
            </view>
          </view>
		  <view class="flex-col justify-start items-start relative section_9 view">
		    <view class="flex-row items-center section_10 space-x-12">
		      <image
		        class="image_2"
		        src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901700541927764165.png"
		      />
		      <view class="flex-col items-start space-y-12">
		        <text class="font_4">MBTI人格测试分析</text>
		        <text class="font_5 text_7">2023.6.15</text>
		      </view>
			  <img class="tupian" src="../../static/jiantou.png" alt="">
		    </view>
		  </view>
		  <view class="flex-col justify-start items-start relative section_9 view">
		    <view class="flex-row items-center section_10 space-x-12">
		      <image
		        class="image_2"
		        src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901700541927764165.png"
		      />
		      <view class="flex-col items-start space-y-12">
		        <text class="font_4">MBTI人格测试分析</text>
		        <text class="font_5 text_7">2023.6.15</text>
		      </view>
		  			  <img class="tupian" src="../../static/jiantou.png" alt="">
		    </view>
		  </view>
		  <view class="flex-col justify-start items-start relative section_9 view">
		    <view class="flex-row items-center section_10 space-x-12">
		      <image
		        class="image_2"
		        src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901700541927764165.png"
		      />
		      <view class="flex-col items-start space-y-12">
		        <text class="font_4">MBTI人格测试分析</text>
		        <text class="font_5 text_7">2023.6.15</text>
		      </view>
		  			  <img class="tupian" src="../../static/jiantou.png" alt="">
		    </view>
		  </view>
          <!-- <view class="flex-col justify-start items-start relative group_7">
            <view class="relative section_11"></view>
            <view class="flex-row section_9 space-x-14 pos">
              <image
                class="image_2"
                src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901700541927764165.png"
              />
              <text class="self-start font_4 text_8">MBTI人格测试分析</text>
            </view>
          </view> -->
        </view>
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
.tupian3{
	padding-left: 198rpx;
	width: 30rpx;
	height: 30rpx;
}
.tupian2{
	padding-left: 203rpx;
	width: 30rpx;
	height: 30rpx;
}
.tupian{
	padding-left: 180rpx;
	width: 30rpx;
	height: 30rpx;
}
.page {
	position: fixed;
    background-color: #f5f5f5;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .group {
      padding: 32rpx 40rpx 0;
      overflow-y: auto;
      .space-y-16 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 32rpx;
        }
        .text_2 {
          margin-left: 12rpx;
        }
        .section {
			border-radius: 25rpx;
          padding: 46rpx 32rpx 24rpx;
          background-color: #ffffff;
          box-shadow: 0px 6rpx 16rpx #a5a5a529;
          .group_2 {
            padding: 0 56rpx;
            .text-wrapper {
              padding: 16rpx 0;
              background-color: #65cbc8;
              border-radius: 40rpx;
              width: 230rpx;
              height: 66rpx;
              .text_3 {
                color: #ffffff;
              }
            }
            .text-wrapper_2 {
              padding: 16rpx 0;
              background-color: #edf2f7;
              border-radius: 40rpx;
              width: 230rpx;
              height: 66rpx;
              .text_4 {
                color: #b0b0b0;
              }
            }
            .font_2 {
              font-size: 40rpx;
              font-family: SegoeUI-Bold;
              line-height: 37rpx;
              font-weight: 700;
            }
          }
          .space-x-20 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 40rpx;
            }
            .space-y-50 {
              & > view:not(:first-child),
              & > text:not(:first-child),
              & > image:not(:first-child) {
                margin-top: 100rpx;
              }
              .text_5 {
                line-height: 31rpx;
              }
            }
            .section_3 {
              margin-top: 148rpx;
              background-color: #d8ebff;
              width: 50rpx;
              height: 268rpx;
            }
          }
          .group_3 {
            margin-top: 32rpx;
            .section_4 {
              margin-top: 280rpx;
              background-color: #d8ebff;
              width: 50rpx;
              height: 136rpx;
            }
            .section_5 {
              margin-top: 404rpx;
              background-color: #d8ebff;
              width: 50rpx;
              height: 10rpx;
            }
            .section_2 {
              background-color: #d8ebff;
              width: 50rpx;
              height: 398rpx;
            }
            .section_6 {
              margin-top: 404rpx;
              background-color: #d8ebff;
              width: 50rpx;
              height: 12rpx;
            }
          }
          .group_4 {
            margin-top: 16rpx;
            padding-left: 68rpx;
            padding-right: 20rpx;
          }
          .font_3 {
            font-size: 36rpx;
            font-family: SegoeUI-Bold;
            line-height: 33rpx;
            font-weight: 700;
            color: #b0b0b0;
          }
          .group_5 {
            margin-top: 44rpx;
            .section_7 {
              background-color: #65cbc8;
              border-radius: 50%;
              width: 22rpx;
              height: 22rpx;
            }
            .section_8 {
              background-color: #b0b0b0;
              border-radius: 50%;
              width: 22rpx;
              height: 22rpx;
            }
          }
        }
      }
      .group_6 {
        margin: 56rpx 0 -94rpx;
        .text_6 {
          margin-left: 12rpx;
          line-height: 45rpx;
        }
        .section_9 {
          background-color: #ffffff;
          border-radius: 24rpx;
          box-shadow: 0px 6rpx 16rpx #93939329;
          .section_10 {
            background-color: #ffffff;
            border-radius: 24rpx;
            box-shadow: 12rpx 6rpx 16rpx #93939329;
            width: 582rpx;
            .space-y-8 {
              & > view:not(:first-child),
              & > text:not(:first-child),
              & > image:not(:first-child) {
                margin-top: 16rpx;
              }
            }
            .font_5 {
              font-size: 44rpx;
              font-family: SegoeUI;
              line-height: 33rpx;
              color: #787a8c;
            }
            .text_7 {
              line-height: 32rpx;
            }
          }
          .image_2 {
            width: 36rpx;
            height: 170rpx;
          }
          .font_4 {
            font-size: 44rpx;
            font-family: SegoeUI;
            line-height: 41rpx;
            color: #787a8c;
          }
          .text_8 {
            margin-top: 48rpx;
          }
        }
        .view {
          margin-top: 36rpx;
        }
        .group_7 {
          padding-top: 36rpx;
          .section_11 {
            background-color: #ffffff;
            border-radius: 24rpx;
            box-shadow: 12rpx 6rpx 16rpx #93939329;
            width: 582rpx;
            height: 170rpx;
          }
          .space-x-14 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 28rpx;
            }
          }
          .pos {
            position: absolute;
            left: 0;
            right: 0;
            top: 36rpx;
          }
        }
      }
      .space-y-12 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 24rpx;
        }
      }
      .font_1 {
        font-size: 48rpx;
        font-family: SegoeUI-Bold;
        line-height: 44rpx;
        font-weight: 700;
        color: #202020;
      }
      .space-x-12 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 24rpx;
        }
      }
    }
  }
</style>
