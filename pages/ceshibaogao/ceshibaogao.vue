<template>
  <view class="flex-col page space-y-12">
<!--    <text class="self-start font_1 text">我的报告</text> -->
    <view class="flex-col section">
      <view class="flex-col group space-y-12">
        <view class="flex-row justify-between items-start">
          <view class="flex-col items-start space-y-14">
            <text class="font_1 text_2">2023.7.9</text>
            <text class="text_4">SDS抑郁自评测试</text>
          </view>
          <view class="flex-row group_2 space-x-18">
            <text class="text_3">1</text>
            <view class="flex-col items-center shrink-0 space-y-32">
              <view class="section_2"></view>
              <text class="font_2 text_5">分</text>
            </view>
          </view>
        </view>
        <text class="self-start font_2 text_6">抑郁：1分</text>
      </view>
      <text class="self-start font_3 text_7">（正常0，轻度1，中度2，严重3）</text>
      <view class="flex-col group_3">
		  
        <view class="flex-col list space-y-16">
          <view class="flex-col section_3" :key="i" v-for="(item, i) in list_u2h0dqFG">
            <view class="flex-col justify-start items-center self-start text-wrapper">
              <text class="font_4 text_8">AI建议</text>
            </view>
            <view class="flex-col group_4 space-y-4">
              <text class="self-end font_3">要想走出抑郁状态，要在对待疾病的态度上做出转变。我们应该逐渐学会宽恕与接纳，感恩疾病让自己明白了很多关于生命的信息，包括如何深度地了解自己、提高个体的力量、丰富思考问题的角度、了解生命的意义等。要想走出抑郁状态，要在对待疾病的态度上做出转变。我们应该逐渐学会宽恕与接纳，感恩疾病让自己明白了很多关于生命的信息，包括如何深度地了解自己、提高个体的力量、丰富思考问题的角度、了解生命的意义等。</text>
            </view>
          </view>
        </view>
		
		<view class="flex-col list space-y-16">
		  <view class="flex-col section_3" >
		    <view class="flex-col justify-start items-center self-start text-wrapper">
		      <text class="font_4 text_8">知识学习</text>
		    </view>
		    <view class="flex-col group_4 space-y-4">
		      <text class="self-end font_3">要想走出抑郁状态，要在对待疾病的态度上做出转变。我们应该逐渐学会宽恕与接纳，感恩疾病让自己明白了很多关于生命的信息，包括如何深度地了解自己、提高个体的力量、丰富思考问题的角度、了解生命的意义等。要想走出抑郁状态，要在对待疾病的态度上做出转变。我们应该逐渐学会宽恕与接纳，感恩疾病让自己明白了很多关于生命的信息，包括如何深度地了解自己、提高个体的力量、丰富思考问题的角度、了解生命的意义等。</text>
		    </view>
		  </view>
		</view>
		
		
        <view class="flex-col section_5">
          <view class="flex-col justify-start items-center self-start text-wrapper_2">
            <text class="font_4 text_12">预约咨询</text>
          </view>
          <view class="flex-row section_6 space-x-12">
            <view class="section_7"></view>
            <view class="flex-col flex-auto group_6 space-y-7">
              <view class="flex-row justify-between items-start">
                <view class="flex-row items-baseline group_7 space-x-6">
                  <text class="text_14">徐老师</text>
                  <text class="text_15">心理咨询师</text>
                </view>
                <view class="flex-col justify-start items-center button"><text class="text_13">预约</text></view>
              </view>
              <view class="flex-row space-x-18">
                <text class="font_5">清华大学</text>
                <text class="font_5 text_16">心理学</text>
              </view>
              <text class="self-start font_5">抑郁症、焦虑症、自闭症咨询...</text>
              <view class="flex-row items-center group_8 space-x-4">
                <image
                  class="image"
                  src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901701527561561730.png"
                />
                <text class="font_6">预约咨询（多点）</text>
              </view>
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
        list_u2h0dqFG: [null],
      };
    },

    methods: {},
  };
</script>

<style scoped lang="scss">
  .page {
    //padding-top: 32rpx;
    background-color: #f5f5f5;
    background-image: url('https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16903615036117643108.png');
    background-size: 100% 100%;
    background-repeat: no-repeat;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .font_1 {
      font-size: 48rpx;
      font-family: SegoeUI-Bold;
      font-weight: 700;
      color: #202020;
    }
    // .text {
    //   margin-left: 136rpx;
    //   line-height: 45rpx;
    // }
    .section {
      padding: 60rpx 38rpx 16rpx;
      background-color: #ffffff;
      box-shadow: 0px 6rpx 12rpx #00000029;
      .group {
        padding: 0 28rpx;
        .space-y-14 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 28rpx;
          }
          .text_2 {
            line-height: 35rpx;
          }
          .text_4 {
            color: #202020;
            font-size: 36rpx;
            font-family: SegoeUI;
            line-height: 33rpx;
          }
        }
        .group_2 {
          margin-right: 36rpx;
          margin-top: 12rpx;
          .text_3 {
            color: #ffa000;
            font-size: 200rpx;
            font-family: SegoeUI;
            line-height: 143rpx;
          }
          .space-y-32 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-top: 64rpx;
            }
            .section_2 {
              background-color: #ffa000;
              border-radius: 50%;
              width: 36rpx;
              height: 36rpx;
            }
            .text_5 {
              line-height: 40rpx;
            }
          }
        }
        .font_2 {
          font-size: 44rpx;
          font-family: SegoeUI;
          color: #202020;
        }
        .text_6 {
          line-height: 41rpx;
        }
      }
      .font_3 {
        font-size: 32rpx;
        font-family: SegoeUI;
        line-height: 38rpx;
        color: #767481;
      }
      .text_7 {
        margin-left: 24rpx;
        margin-top: 16rpx;
        color: #b0b0b0;
        line-height: 31rpx;
      }
      .group_3 {
        margin-top: 28rpx;
        .list {
          padding-bottom: 30rpx;
          .section_3 {
            padding: 24rpx 12rpx 0;
            background-color: #edf1f6;
            border-radius: 24rpx;
            .text-wrapper {
              //padding-top: 24rpx;
              background-color: #65cbc8;
              border-radius: 32rpx;
              width: 200rpx;
              height: 60rpx;
              .text_8 {
                // line-height: 60rpx;
				margin: auto auto;
              }
            }
            .group_4 {
              padding: 20rpx 20rpx 30rpx 20rpx;
            }
            .space-y-4 {
              & > view:not(:first-child),
              & > text:not(:first-child),
              & > image:not(:first-child) {
                margin-top: 8rpx;
              }
            }
          }
        }
        .space-y-16 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 32rpx;
          }
        }
        .section_5 {
          padding: 26rpx 24rpx 42rpx;
          background-color: #edf1f6;
          border-radius: 24rpx;
          .text-wrapper_2 {
            padding: 16rpx 0 16rpx;
            background-color: #65cbc8;
            border-radius: 32rpx;
            width: 200rpx;
            .text_12 {
			  margin: auto auto;
              line-height: 37rpx;
            }
          }
          .section_6 {
            margin: 16rpx 8rpx 0;
            padding: 16rpx 20rpx;
            background-color: #ffffff;
            border-radius: 40rpx;
            box-shadow: 0px 10rpx 6rpx #00000029;
            .section_7 {
              background-color: #ebebeb;
              border-radius: 40rpx;
              width: 154rpx;
              height: 154rpx;
            }
            .group_6 {
              margin-right: 10rpx;
              .group_7 {
                margin-top: 16rpx;
                .text_14 {
                  color: #202020;
                  font-size: 36rpx;
                  font-family: SegoeUI-Bold;
                  font-weight: 700;
                  line-height: 33rpx;
                }
                .text_15 {
                  color: #202020;
                  font-size: 28rpx;
                  font-family: SegoeUI-Bold;
                  font-weight: 700;
                  line-height: 26rpx;
                }
              }
              .space-x-6 {
                & > view:not(:first-child),
                & > text:not(:first-child),
                & > image:not(:first-child) {
                  margin-left: 12rpx;
                }
              }
              .button {
                padding: 8rpx 0;
                background-color: #96a1f9;
                border-radius: 60rpx;
                width: 78rpx;
                height: 36rpx;
                .text_13 {
                  color: #ebebeb;
                  font-size: 22rpx;
                  font-family: SegoeUI-Bold;
                  font-weight: 700;
                  line-height: 20rpx;
                }
              }
              .group_8 {
                padding: 0 4rpx;
                .image {
                  width: 24rpx;
                  height: 24rpx;
                }
                .font_6 {
                  font-size: 20rpx;
                  font-family: SegoeUI;
                  line-height: 19rpx;
                  color: #000000;
                }
              }
              .space-x-4 {
                & > view:not(:first-child),
                & > text:not(:first-child),
                & > image:not(:first-child) {
                  margin-left: 8rpx;
                }
              }
            }
            .space-y-7 {
              & > view:not(:first-child),
              & > text:not(:first-child),
              & > image:not(:first-child) {
                margin-top: 14rpx;
              }
            }
          }
          .space-x-12 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 24rpx;
            }
          }
        }
        .font_4 {
          font-size: 40rpx;
          font-family: SegoeUI-Bold;
          line-height: 38rpx;
          font-weight: 700;
          color: #ffffff;
        }
      }
      .space-x-18 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 36rpx;
        }
        .text_16 {
          line-height: 18rpx;
        }
      }
      .font_5 {
        font-size: 20rpx;
        font-family: SegoeUI;
        line-height: 19rpx;
        color: #202020;
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
  .space-y-12 {
    & > view:not(:first-child),
    & > text:not(:first-child),
    & > image:not(:first-child) {
      margin-top: 24rpx;
    }
  }
</style>