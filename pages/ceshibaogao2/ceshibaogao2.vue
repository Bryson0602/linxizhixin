<template>
  <view class="flex-col page space-y-12">
<!--    <text class="self-start font_1 text">我的报告</text> -->
    <view class="flex-col section">
      <view class="flex-col group space-y-12">
        <view class="flex-row justify-between items-start">
          <view class="flex-col items-start space-y-14">
            <text class="font_1 text_2">{{currentTime}}</text>
            <text class="text_4">{{this.ArrList[0].name}}</text>
          </view>
          <view class="flex-row group_2 space-x-18">
            <text class="text_3">{{this.score}}</text>
            <view class="flex-col items-center shrink-0 space-y-32">
              <view class="section_2"></view>
              <text class="font_2 text_5">分</text>
            </view>
          </view>
        </view>
        <text class="self-start font_2 text_6">得分：{{this.score}}分</text>
      </view>
      <text class="self-start font_3 text_7">{{this.ArrList[0].shuomin}}</text>
      <view class="flex-col group_3">
		  
        <view class="flex-col list space-y-16">
          <view class="flex-col section_3" :key="i" v-for="(item, i) in list_u2h0dqFG">
            <view class="flex-col justify-start items-center self-start text-wrapper">
              <text class="font_4 text_8">AI建议</text>
            </view>
            <view class="flex-col group_4 space-y-4">
              <text class="self-end font_3" v-if="score >= 14 && score <= 28">{{text1}}</text>
              <text class="self-end font_3" v-else-if="score >= 29 && score <= 42">{{text2}}</text>
              <text class="self-end font_3" v-else-if="score >= 43 && score <= 56">{{text3}}</text>
              <text class="self-end font_3" v-else-if="score >= 57">{{text4}}</text>
            </view>
          </view>
        </view>
		
		<view class="flex-col list space-y-16">
		  <view class="flex-col section_3 section_4" >
		    <view class="flex-col justify-start items-center self-start text-wrapper text-wrapper_3">
		      <text class="font_4 text_8">知识学习</text>
		    </view>
		    <view class="flex-col group_4 space-y-4">
		      <text class="self-end font_3">{{this.ArrList[0].learning}}</text>
		    </view>
			<view class="flex-row xuexi" @click="goxuexi">
				<view class="img">
					<image src="../../static/wjj.jpeg" mode=""></image>
				</view>
				<view class="flex-col wenzi">
					<text class="zsxx">知识学习 | 学习更多</text>
					<text class="wt">心理压力太大怎么办？</text>
				</view>
				<view class="img1 flex-col">
					<image src="../../static/youjiantou.png" mode=""></image>
				</view>
			</view>
		  </view>
		</view>
		
		
        <view class="flex-col section_5">
          <view class="flex-col justify-start items-center self-start text-wrapper_2">
            <text class="font_4 text_12">预约咨询</text>
          </view>
          <view class="flex-row section_6 space-x-12" @click="goyuyue">
            <view class="section_7">
				<image src="../../static/teacher.png" mode=""></image>
			</view>
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
		
		<text class="ys">——灵犀知心全力保护您的隐私——</text>
      </view>
    </view>
  </view>
</template>

<script>
  import dayjs from 'dayjs'
  export default {
    components: {},
    data() {
      return {
		currentTime: '',
		score: 0,  
		text:'',
		text1:'',
		text2:'',
		text3:'',
		text4:'',
		ArrList: [],
        list_u2h0dqFG: [null],
      };
    },

    methods: {
		//获取网络数据
		getData(){
			uni.request({
				url:"https://fc-mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.next.bspapp.com/PSS_plus",
				success:res=>{
					console.log(res);
					this.ArrList=res.data.data
					this.text1=this.ArrList[0].suggestion1
					this.text2=this.ArrList[0].suggestion2
					this.text3=this.ArrList[0].suggestion3
					this.text4=this.ArrList[0].suggestion4
					//console.log(this.text1);
				}
			})
		},
		goxuexi(){
			uni.navigateTo({
				url:"/pages/xuexi3/xuexi3?id=64bfbbbb86206658e9a21e6c"
			})
		},
		goyuyue(){
			uni.navigateTo({
				url:"/pages/yuyue/yuyue?id=64bf388fe0ec19bea1385782"
			})
		}

	},
	onLoad(option) {
		this.getData();
		//接受分数
		const score = option.score;
		this.score = score
	},
    mounted() {
	    this.currentTime = dayjs().format('YYYY.M.D')
		// if(this.score > 14) {
		// 	this.text = this.text1;
		// } else if(this.score > 9) {
		// 	this.text = this.text2;
		// } else if(this.score > 4) {
		// 	this.text = this.text3;
		// } else {
		// 	this.text = this.text4;
		// }  
    }
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
          margin-right: 0rpx;
          margin-top: 12rpx;
          .text_3 {
            color: #fa8a3a;
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
              background-color: #fa8a3a;
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
             //background-color: #edf1f6;
			background: linear-gradient(
			    to bottom right, 
			    #eafbff 0%,
			    #edfbff 20%,
			    #edfbfe 40%,
			    #e8f8fe 60%,
			    #eaf1fb 80%,
			    #e8e6fb 100%
			  );
            border-radius: 24rpx;
			.xuexi{
				margin-bottom: 30rpx;
				margin-right: 20rpx;
				margin-left: 20rpx;
				background-color: #ffffff;
				border-radius: 24rpx;
				//width: 100%;
				height: 150rpx;
				position: relative;
				.img{
					margin:15rpx 0 15rpx 15rpx ;
					background-color: #dbf3f7;
					width: 120rpx;
					height: 120rpx;
					border-radius: 24rpx;
					overflow: hidden;
					image{
					    width: 120rpx;
					    height: 120rpx;
					}
				}
				.wenzi{
					//margin-right: 30rpx;
					.zsxx{
						margin-left: 30rpx;
						margin-top: 30rpx;
						font-size: 20rpx;
						color: #8a8a8a;
					}
					.wt{
						margin-left: 30rpx;
						margin-top: 10rpx;
						font-size: 30rpx;
						font-weight: 700;
						color: #3f3f3f;
					}
				}
				.img1{
					right: 15rpx;
					top: 15rpx;
					position: absolute;
					//margin:15rpx 15rpx 0 15rpx ;
					background-color: #d0d0d0;
					width: 70rpx;
					height: 45rpx;
					border-radius: 15rpx;
					overflow: hidden;
					image{
						margin: auto auto;
					    width: 25rpx;
					    height: 25rpx;
					}
				}
			}
            .text-wrapper {
              //padding-top: 24rpx;
              background-color: #88c6ee;
              border-radius: 32rpx;
              width: 200rpx;
              height: 60rpx;
              .text_8 {
                // line-height: 60rpx;
				margin: auto auto;
              }
            }
			.text-wrapper_3{
				background-color: #a1b6d5;
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
		  .section_4{
			  background: #edf1f6;
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
            background-color: #a1b6d5;
            border-radius: 32rpx;
            width: 200rpx;
            .text_12 {
			  margin: auto auto;
              line-height: 37rpx;
            }
          }
          .section_6 {
            margin: 16rpx 8rpx 0;
            padding: 16rpx 15rpx;
            background-color: #ffffff;
            border-radius: 24rpx;
            box-shadow: 0px 4rpx 4rpx #00000029;
            .section_7 {
              background-color: #ebebeb;
              border-radius: 24rpx;
			  margin: auto 0;
              width: 120rpx;
              height: 120rpx;
			  overflow: hidden;
			  image{
				width: 120rpx;
				height: 120rpx;
			  }
            }
            .group_6 {
              margin-right: 0rpx;
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
                border-radius: 15rpx;
                width: 70rpx;
                height: 45rpx;
                .text_13 {
                  color: #ebebeb;
                  font-size: 22rpx;
                  font-family: SegoeUI-Bold;
                  font-weight: 700;
                  line-height: 30rpx;
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
		.ys{
			margin: 40rpx auto;
			color: #797979;
			font-size: 30rpx;
		}
        .font_4 {
          font-size: 36rpx;
          font-family: SegoeUI-Bold;
          line-height: 38rpx;
          font-weight: 600;
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