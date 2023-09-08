<template>
  <view class="flex-col page space-y-13">
    <view class="flex-row justify-center items-center relative group">
      <!-- <text class="text">圈子</text> -->
      <image
        class="image pos"
        src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385887396145539.png"
      />
    </view>
    <view class="flex-col space-y-18">
      <view class="flex-col section">
        <view class="flex-row justify-between items-center group_2">
          <view class="flex-row space-x-8">
            <view class="flex-col justify-start items-center text-wrapper"><text class="font_2">热门</text></view>
            <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_1">校园</text></view>
            <view class="flex-col justify-start items-center text-wrapper_2">
              <text class="font_1 text_2">生活</text>
            </view>
          </view>
          <view class="flex-row items-center space-x-4">
            <text class="font_2 text_3">全部</text>
            <image
              class="shrink-0 image_2"
              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385886079491941.png"
            />
          </view>
        </view>
        <view class="grid">
          <view class="flex-col grid-item space-y-14">
            <view class="section_2">
				<image src="../../static/yuan.png" mode="" class="section_2"></image>
			</view>
            <text class="self-center font_2">动漫二次元</text>
            <text class="self-center font_3">2000人关注</text>
          </view>
          <view class="flex-col grid-item">
            <view class="section_2">
				<image src="../../static/dianyin.png" mode="" class="section_2"></image>
			</view>
            <text class="self-center font_2 text_4">影视发烧迷</text>
            <text class="self-center font_3 text_6">200人关注</text>
          </view>
          <view class="flex-col grid-item">
            <view class="section_2">
				<image src="../../static/jianshen3.png" mode="" class="section_2"></image>
			</view>
            <text class="self-center font_2 text_5">健身俱乐部</text>
            <text class="self-center font_3 text_7">100人关注</text>
          </view>
          <view class="flex-col grid-item_2">
            <view class="relative section_2">
				<image src="../../static/mao.png" mode="" class="section_2"></image>
			</view>
            <view class="flex-col items-center group_3 space-y-12">
              <text class="font_2">宠物交流会</text>
              <text class="font_3">150人关注</text>
            </view>
          </view>
          <view class="flex-col grid-item_2">
            <view class="relative section_2">
				<image src="../../static/chenshi3.png" mode="" class="section_2"></image>
			</view>
            <view class="flex-col items-center group_3 space-y-12">
              <text class="font_2">城市游玩会</text>
              <text class="font_3">800人关注</text>
            </view>
          </view>
          <view class="flex-col grid-item_2">
            <view class="relative section_2">
				<image src="../../static/jiu2.png" mode="" class="section_2"></image>
			</view>
            <view class="flex-col items-center group_3 space-y-12">
              <text class="font_2">日咖夜酒</text>
              <text class="font_3">666人关注</text>
            </view>
          </view>
        </view>
      </view>
      <view  class="flex-col section_3 space-y-24">
        <view class="flex-col group_4 space-y-4">
          <view class="flex-row justify-between">
            <view class="flex-row items-center space-x-10">
              <image src="../../static/tx11.jpeg" mode="" class="section_4"></image>
              <view class="flex-col space-y-12">
                <text class="self-start font_2">好想吃饭</text>
                <view class="flex-row space-x-6">
                  <text class="font_4">2023-7-8</text>
                  <text class="font_4">15：22</text>
                </view>
              </view>
            </view>
            <view @click="change" v-if="status" class="flex-col justify-start items-center self-start text-wrapper_3">
              <text class="font_2 text_8">关注</text>
            </view>
			<view @click="change" v-else class="flex-col justify-start items-center self-start text-wrapper_3">
			  <text class="font_2 text_8">已关注</text>
			</view>
          </view>
          <text class="self-start text_9">来自宠物交流会</text>
        </view>
        <view @click="togou" class="flex-col">
          <view class="flex-col items-start group_5 space-y-4">
            <text class="font_5">小狗狗真是太可爱了，尤其是小金毛，就算今天心情不</text>
            <text class="font_5">好也能立马被小动物们治愈啊QAQ...</text>
          </view>
          <text class="self-start font_66 text_10">...</text>
          <view class="flex-row equal-division space-x-10">
            <view class="equal-division-item space-y-16">
              <view class="section_5">
				  <image src="../../static/gou3.png" mode="" class="section_5"></image>
			  </view>
			  <image src="../../static/fenxiang.png" class="tupian1"></image>
              <text class="self-center font_6 text_11">转发</text>
            </view>
            <view class="equal-division-item space-y-16">
              <view class="section_5">
				  <image src="../../static/gou1.png" mode="" class="section_5"></image>
			  </view>
			  <image src="../../static/liaoyiliao3.png" class="tupian2"></image>
              <text class="self-center font_6 text_11">130</text>
            </view>
            <view class="equal-division-item space-y-16">
              <view class="section_5">
				  <image src="../../static/gou2.png" mode="" class="section_5"></image>
			  </view>
			  <image src="../../static/dianzan.png" class="tupian3"></image>
              <text class="self-center font_6 text_11">300</text>
            </view>
          </view>
        </view>
      </view>
	  <view class="flex-col section_3 space-y-24">
	    <view class="flex-col group_4 space-y-4">
	      <view class="flex-row justify-between">
	        <view class="flex-row items-center space-x-10">
	          <image src="../../static/tx12.jpeg" mode="" class="section_4"></image>
	          <view class="flex-col space-y-12">
	            <text class="self-start font_2">不想睡觉</text>
	            <view class="flex-row space-x-6">
	              <text class="font_4">2023-9-1</text>
	              <text class="font_4">13：22</text>
	            </view>
	          </view>
	        </view>
	        <view v-if="status1" @click="change1" class="flex-col justify-start items-center self-start text-wrapper_3">
	          <text class="font_2 text_8">关注</text>
	        </view>
			<view @click="change1" v-else class="flex-col justify-start items-center self-start text-wrapper_3">
			  <text class="font_2 text_8">已关注</text>
			</view>
	      </view>
	      <text class="self-start text_9">来自宠物交流会</text>
	    </view>
	    <view class="flex-col">
	      <view class="flex-col items-start group_5 space-y-4">
	        <text class="font_5">总要去趟重庆吧！</text>
	        <text class="font_5">吹一吹嘉陵江的晚风，走走南滨路，感受山城的热情</text>
	      </view>
	      <text class="self-start font_66 text_10">...</text>
	      <view class="flex-row equal-division space-x-10">
	        <view class="equal-division-item space-y-16">
	          <view class="section_5">
	  				  <image src="../../static/yejin3.png" mode="" class="section_5"></image>
	  			  </view>
	  			  <image src="../../static/fenxiang.png" class="tupian4"></image>
	          <text class="self-center font_6 text_11">转发</text>
	        </view>
	        <view class=" equal-division-item space-y-16">
	          <view class="section_5">
	  				  <image src="../../static/yejin2.png" mode="" class="section_5"></image>
	  			  </view>
	  			  <image src="../../static/liaoyiliao3.png" class="tupian5"></image>
	          <text class="self-center font_6 text_11">30</text>
	        </view>
	        <view class=" equal-division-item space-y-16">
	          <view class="section_5">
	  				  <image src="../../static/yejin.png" mode="" class="section_5"></image>
	  			  </view>
	  			  <image src="../../static/dianzan.png" class="tupian6"></image>
	          <text class="self-center font_6 text_11">90</text>
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
		  status:true,
		  status1:true
	  };
    },

    methods: {
		change(){
			this.status=!this.status
		},
		change1(){
			this.status1=!this.status1
		},
		togou(){
			uni.navigateTo({
				url:'/pages/quanzi2/quanzi2?status='+this.status
			})
		}
	},
  };
</script>

<style scoped lang="scss">
	.tupian1{
		margin-bottom: -6rpx;
		margin-left: 40rpx;
		width: 35rpx;
		height: 35rpx;
	}
	.tupian2{
		margin-bottom: -6rpx;
	margin-left: 40rpx;
		width: 35rpx;
		height: 35rpx;
	}
	.tupian3{
		margin-bottom: -6rpx;
	margin-left: 40rpx;
		width: 35rpx;
		height: 35rpx;
	}
	.tupian4{
		margin-bottom: -6rpx;
		margin-left: 40rpx;
		width: 35rpx;
		height: 35rpx;
	}
	.tupian5{
		margin-bottom: -6rpx;
		margin-left: 40rpx;
		width: 35rpx;
		height: 35rpx;
	}
	.tupian6{
		margin-bottom: -6rpx;
		margin-left: 40rpx;
		width: 35rpx;
		height: 35rpx;
	}
  .page {
    padding: 24rpx 24rpx 60rpx;
    background-color: #edeff1;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .group {
      padding: 12rpx 18rpx 8rpx;
      .text {
        color: #202020;
        font-size: 40rpx;
        font-family: SegoeUI-Bold;
        font-weight: 700;
        line-height: 35rpx;
      }
      .image {
        width: 54rpx;
        height: 54rpx;
      }
      .pos {
        position: absolute;
        right: 18rpx;
        top: 50%;
        transform: translateY(-50%);
      }
    }
    .space-y-18 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 36rpx;
      }
      .section {
        padding: 14rpx 0 32rpx;
        background-color: #ffffff;
        border-radius: 60rpx;
        .group_2 {
          padding-left: 26rpx;
          padding-right: 18rpx;
          .space-x-8 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 16rpx;
            }
            .text-wrapper {
              padding: 32rpx 0;
              background-color: #65cbc8;
              border-radius: 50%;
              width: 90rpx;
              height: 90rpx;
            }
            .text-wrapper_2 {
              padding: 32rpx 0;
              background-color: #ebebeb;
              border-radius: 50%;
              width: 90rpx;
              height: 90rpx;
              .text_2 {
                line-height: 29rpx;
              }
            }
            .font_1 {
              font-size: 32rpx;
              font-family: SegoeUI-Bold;
              line-height: 30rpx;
              font-weight: 700;
              color: #78708c;
            }
			.font_2 {
			  font-size: 32rpx;
			  font-family: SegoeUI-Bold;
			  line-height: 30rpx;
			  font-weight: 700;
			  color: #fff;
			}
          }
          .space-x-4 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 8rpx;
            }
            .text_3 {
              color: #707070;
            }
            .image_2 {
              width: 36rpx;
              height: 36rpx;
            }
          }
        }
        .grid {
          height: 656rpx;
          display: grid;
          grid-template-columns: repeat(3, 1fr);
          column-gap: 12rpx;
          .grid-item {
            padding: 24rpx;
            .text_4 {
              margin-top: 32rpx;
            }
            .text_6 {
              margin-top: 20rpx;
            }
            .text_5 {
              margin-top: 32rpx;
            }
            .text_7 {
              margin-top: 20rpx;
            }
          }
          .space-y-14 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-top: 28rpx;
            }
          }
          .grid-item_2 {
            padding: 12rpx 24rpx 0;
            .group_3 {
              padding: 40rpx 0 20rpx;
            }
          }
          .section_2 {
            background-color: #dbdbdb;
            border-radius: 40rpx;
            box-shadow: 0px 6rpx 12rpx #00000029;
            height: 178rpx;
			width: 178rpx;
          }
          .font_3 {
            font-size: 24rpx;
            font-family: SegoeUI-Bold;
            line-height: 22rpx;
            font-weight: 700;
            color: #acb9cd;
          }
        }
      }
      .section_3 {
        padding: 22rpx 0 32rpx;
        background-color: #ffffff;
        border-radius: 60rpx;
        .group_4 {
          padding: 0 28rpx;
          .text-wrapper_3 {
            margin-right: 12rpx;
            padding: 12rpx 0;
            background-color: #65cbc8;
            border-radius: 40rpx;
            width: 116rpx;
            height: 52rpx;
            .text_8 {
              color: #ffffff;
            }
          }
          .text_9 {
            margin-left: 120rpx;
            color: #ffffff;
            font-size: 18rpx;
            font-family: SegoeUI-Bold;
            font-weight: 700;
            line-height: 17rpx;
          }
        }
        .space-y-4 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 8rpx;
          }
        }
        .group_5 {
          padding-left: 16rpx;
          padding-right: 12rpx;
        }
        .font_5 {
          font-size: 28rpx;
          font-family: SegoeUI-Bold;
          line-height: 34rpx;
          font-weight: 700;
          color: #202020;
        }
		.font_66 {
			opacity: 0;
		  font-size: 28rpx;
		  font-family: SegoeUI-Bold;
		  line-height: 34rpx;
		  font-weight: 700;
		  color: #202020;
		}
        .text_10 {
          margin-left: 16rpx;
          margin-top: 20rpx;
        }
        .equal-division {
          padding: 0 18rpx;
          .equal-division-item {
            flex: 1 1 222rpx;
            padding: 8rpx;
            .section_5 {
              background-color: #dbdbdb;
              border-radius: 40rpx;
              height: 192rpx;
			  width: 192rpx;
            }
            .font_6 {
              font-size: 32rpx;
              font-family: SegoeUI-Bold;
              line-height: 22rpx;
              font-weight: 700;
              color: #707070;
            }
            .text_11 {
				margin-left: 6rpx;
              line-height: 23rpx;
            }
          }
          .space-y-16 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-top: 32rpx;
            }
          }
        }
        .space-x-10 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-left: 20rpx;
          }
          .section_4 {
            background-color: #dbdbdb;
            border-radius: 50%;
            width: 96rpx;
            height: 96rpx;
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
      .space-y-12 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 24rpx;
        }
        .space-x-6 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-left: 12rpx;
          }
          .font_4 {
            font-size: 24rpx;
            font-family: SegoeUI-Bold;
            line-height: 18rpx;
            font-weight: 700;
            color: #a9a9a9;
          }
        }
      }
      .font_2 {
        font-size: 32rpx;
        font-family: SegoeUI-Bold;
        line-height: 30rpx;
        font-weight: 700;
        color: #202020;
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