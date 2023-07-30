<template>
  <view class="flex-col page">
    <view class="flex-col flex-auto group">
      <view class="flex-row  self-start section ">
        <image class="ai" src="../../static/newai.png" mode="widthFix"></image>
        <text class="self-start font_1 text_2">根据您的选择，AI智能推荐你进行以下测试：</text>
      </view>
	  
      <view class="flex-col group_2">
        <view class="flex-col justify-start relative group_3">
          <view class="relative section_5"></view>
          <view class="section_3 pos_2"></view>
          <view class="flex-row items-center section_2 space-x-12 pos">
            <view class="flex-col items-start flex-auto">
              <text class="text_3">SDS抑郁自评测试</text>
              <text class="font_2 text_5">抑郁自评量表（Self-rating depression scale），是含有20个项目，分为4级评分的自评量表，原型是W.K.Zung...</text>
            </view>
            <view class="flex-col items-center shrink-0 section_4 space-y-12" @click="goceshi">
              <text class="font_1 text_4">开始测试</text>
              <image
                class="image_2"
                src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901701522453211676.png"
              />
            </view>
          </view>
        </view>
        <view class="flex-row justify-between items-start group_4">
          <view class="flex-row items-center button space-x-2">
            <!-- <image
              class="shrink-0 image"
              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901701522396056428.png"
            /> -->
            <text class="font_1 font_5">其他测试</text>
          </view>
          <!-- <text class="text_9">不知如何选择？点这里</text> -->
        </view>
        <view class="flex-col list space-y-18">
			
          <view class="flex-row justify-start items-start list-item" @click="goceshi">
            <view class="flex-row section_6">
              <image
                class="image_3"
                src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901701522414704453.png"
              />
              <view class="flex-auto flex-col items-start self-start group_5">
                <text class="font_3">PHQ-9(抑郁自评测试)</text>
                <text class="font_4 text_10">PHQ-9抑郁自评量表，用于评估个体是否存在抑郁症状及其严重程度。</text>
                <!-- <text class="font_4 text_11"></text> -->
              </view>
            </view>
			<image class="jiantou" src="../../static/jiantou.png" mode="widthFix"></image>
          </view>
		  
		  <view class="flex-row justify-start items-start list-item" @click="goceshi1">
		    <view class="flex-row section_6">
		      <image class="image_3" src="../../static/bq-yellow.png" mode=""></image>
		      <view class="flex-auto flex-col items-start self-start group_5">
		        <text class="font_3">GAD7(焦虑障碍量表)</text>
		        <text class="font_4 text_10">焦虑症自评量表，用于评估个体是否存在焦虑症状，由7个问题组成。</text>
		        <!-- <text class="font_4 text_11"></text> -->
		      </view>
		    </view>
		  			<image class="jiantou" src="../../static/jiantou.png" mode="widthFix"></image>
		  </view>
		  
		  <view class="flex-row justify-start items-start list-item" @click="goceshi2">
		    <view class="flex-row section_6">
		      <image class="image_3" src="../../static/bq-pink.png" mode=""></image>
		      <view class="flex-auto flex-col items-start self-start group_5">
		        <text class="font_3">PSS(心理压力量表)</text>
		        <text class="font_4 text_10">心理压力自评量表，用于评估个体对生活中的压力感知程度。</text>
		        <!-- <text class="font_4 text_11"></text> -->
		      </view>
		    </view>
		  			<image class="jiantou" src="../../static/jiantou.png" mode="widthFix"></image>
		  </view>
		  
		  <view class="flex-row justify-start items-start list-item" @click="goceshi1">
		    <view class="flex-row section_6">
		      <image class="image_3" src="../../static/bq-green.png" mode=""></image>
		      <view class="flex-auto flex-col items-start self-start group_5">
		        <text class="font_3">MBTI人格自测</text>
		        <text class="font_4 text_10">人格自测工具，用于评估个体的人格类型。测量结果基于四个维度的偏好。</text>
		        <!-- <text class="font_4 text_11"></text> -->
		      </view>
		    </view>
		  			<image class="jiantou" src="../../static/jiantou.png" mode="widthFix"></image>
		  </view>
		  
		  <view class="flex-row justify-start items-start list-item" @click="goceshi1">
		    <view class="flex-row section_6">
		      <image class="image_3" src="../../static/bq-huang.png" mode=""></image>
		      <view class="flex-auto flex-col items-start self-start group_5">
		        <text class="font_3">GAD7焦虑障碍量表</text>
		        <text class="font_4 text_10">焦虑症自评量表，用于评估个体是否存在焦虑症状，由7个问题组成。</text>
		        <!-- <text class="font_4 text_11"></text> -->
		      </view>
		    </view>
		  			<image class="jiantou" src="../../static/jiantou.png" mode="widthFix"></image>
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
        list_cHax5sNc: [null, null, null, null, null, null],
      };
    },

    methods: {
		goceshi(){
			uni.navigateTo({
				url:'/pages/sdszice/sdszice'
			})
		},
		goceshi1(){
			uni.navigateTo({
				url:'/pages/zice1/zice1'
			})
		},
		goceshi2(){
			uni.navigateTo({
				url:'/pages/zice2/zice2'
			})
		},
	},
  };
</script>

<style scoped lang="scss">
  .page {
	position: fixed;
    background-color: #f5f5f5;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .group {
      padding: 22rpx 36rpx 300rpx 36rpx;
      overflow-y: auto;
      .section {
		width: 100%;
		// height: 100%;
        background-color: #ecfdfd;
        border-radius: 32rpx;
        box-shadow: 0px 6rpx 16rpx #a5a5a529;
		.ai{
			width: 80rpx;
			margin: auto 0;
			margin-left: 10rpx;
		}
        .text_2 {
		  //width: 100%;
		  flex: 1;
          margin-left: 10rpx;
		  margin-right: 20rpx;
		  font-size: 32rpx;
		  color: #363636;
          margin-top: 20rpx;
		  margin-bottom: 20rpx;
		  line-height: 40rpx;
        }
      }
      .group_2 {
        margin: 42rpx 0 -90rpx;
        .group_3 {
          padding-top: 32rpx;
          .section_5 {
            margin-right: 4rpx;
            background-color: #fff8ff;
            border-radius: 40rpx;
            box-shadow: 0px 6rpx 12rpx #00000029;
            height: 272rpx;
          }
          .section_3 {
            background-color: #be9ed2;
            border-radius: 40rpx;
            box-shadow: 0px 6rpx 12rpx #00000029;
            height: 272rpx;
          }
          .pos_2 {
            position: absolute;
            left: 0;
            right: 5rpx;
            top: 50%;
            transform: translateY(-50%);
          }
          .section_2 {
            padding: 24rpx 16rpx;
            background-color: #6453ce;
            border-radius: 40rpx;
            box-shadow: 0px 6rpx 12rpx #00000029;
            .text_3 {
              margin-left: 16rpx;
              color: #ffffff;
              font-size: 40rpx;
              font-family: SegoeUI-Bold;
              font-weight: 700;
              line-height: 37rpx;
            }
            .font_2 {
              font-size: 20rpx;
              font-family: SegoeUI;
              line-height: 24rpx;
              color: #d8d8d8;
            }
            .text_5 {
			  margin-left: 20rpx;
			  margin-right: 20rpx;
              margin-top: 20rpx;
            }
            .section_4 {
              margin-right: 8rpx;
              padding: 32rpx 0;
              background-color: #be9ed2;
              border-radius: 40rpx;
              width: 230rpx;
              height: 220rpx;
              .text_4 {
                color: #ffffff;
              }
              .image_2 {
                width: 60rpx;
                height: 100rpx;
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
          .space-x-12 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 24rpx;
            }
          }
          .pos {
            position: absolute;
            left: 0;
            right: 5rpx;
            top: 0;
          }
        }
        .group_4 {
          margin-top: 40rpx;
          .button {
            background-color: #ffffff;
            border-radius: 32rpx;
            box-shadow: 0px 16rpx 16rpx #a5a5a529;
            //width: 252rpx;
            height: 80rpx;
          }
          .space-x-2 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 4rpx;
            }
          }
          // .text_9 {
          //   margin-top: 68rpx;
          //   color: #787a8c;
          //   font-size: 28rpx;
          //   font-family: SegoeUI;
          //   line-height: 26rpx;
          // }
        }
        .list {
          margin-top: 24rpx;
          .list-item {
            margin-right: 4rpx;
            background-color: #ffffff;
            border-radius: 24rpx;
            box-shadow: 0px 6rpx 16rpx #93939329;
			.jiantou{
				  //flex: 1;
				  //margin-left: 600rpx;
				  margin: auto auto;
				  width: 50rpx;
			  }
            .section_6 {
              background-color: #ffffff;
              border-radius: 24rpx;
              box-shadow: 12rpx 6rpx 16rpx #93939329;
			  width: 85%;
			  
              .image_3 {
                width: 36rpx;
                height: 170rpx;
              }
              .group_5 {
                margin: 26rpx 8rpx 0 24rpx;
				//padding-right: 28rpx;
                .font_3 {
                  font-size: 44rpx;
                  font-family: SegoeUI;
                  line-height: 41rpx;
                  color: #202020;
                }
                .font_4 {
                  font-size: 25rpx;
                  font-family: SegoeUI;
                  line-height: 35rpx;
                  color: #787a8c;
                }
                .text_10 {
				  width: 100%;
                  margin-top: 16rpx;
                }
                // .text_11 {
                //   margin-top: 4rpx;
                // }
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
      }
      .font_1 {
        font-size: 36rpx;
        font-family: SegoeUI;
        line-height: 33rpx;
        color: #202020;
      }
	  .font_5 {
	    font-family: SegoeUI;
		margin-left: 20rpx;
		margin-right: 20rpx;
		font-size: 32rpx;
		color: #363636;
		margin-top: 20rpx;
		margin-bottom: 20rpx;
		line-height: 40rpx;
		font-weight: 500;
	  }
      .image {
        filter: drop-shadow(0px 6rpx 8rpx #a5a5a529);
        width: 52rpx;
        height: 80rpx;
      }
    }
  }
</style>