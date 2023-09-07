<template>
  <view class="flex-col page space-y-416">
    <view class="flex-row items-center section space-x-14">
      <view class="section_2">
		  <image src="../../static/tx11.jpeg" mode="" class="section_2"></image>
	  </view>
      <text class="font_1 text">好想吃饭</text>
	  <view v-if="status" class="guanzhu">
	  	 <text  class="font_22 text_" @click="change">关注</text>
	  </view>
	  <view v-else class="guanzhued">
		  <text  class="font_23" @click="change">已关注</text>
	  </view>
	  
	  <image src="../../static/fenxiang.png" mode="" class="tupian2"></image>
    </view>
	<!-- <image src="../../static/gou4.png" mode="" class="tupian"></image> -->
	
		<view class="swiper-container">
			<view class="swiper-container">
			  <swiper class="my-swiper" :style="swiperStyle" :indicator-dots="true" :autoplay="false" indicator-color=white :duration="500" @change="swiperChange">
			    <swiper-item v-for="(item, index) in imageList" :key="index">
			    <image :src="item" mode="aspectFit" class="da"></image>
			    </swiper-item>
			  </swiper>
			  </view>
		</view>
		
	
	    
		
    <view class="flex-col section_3 space-y-102">
      <view class="flex-col self-start group">
        <view>
          <text class="font_2 text_2">小狗狗真是太可爱了</text>
		  </br>
          <text class="font_1">尤其是小金毛，就算今天心情不</text>
          <text class="font_1">好也能立马被小动物们治愈啊QAQ</text>
          <text class="font_1">...</text>
          <text class="font_1">...</text>
        </view>
        <view class="flex-col justify-start self-start relative text-wrapper">
          <!-- <text class="font_3 text_3">来自宠物交流会</text> -->
        </view>
      </view>
      <view class="flex-row items-center group_2 space-x-20">
        <view class="flex-row items-center flex-auto space-x-7">
          <view class="shrink-0 section_4">
			  <image src="../../static/shx.jpg" mode="" class="shrink-0 section_4"></image>
		  </view>
          <view class="flex-col justify-start items-start flex-auto text-wrapper_2">
            <text class="font_3 text_6">说些什么吧...</text>
          </view>
        </view>
        <view class="flex-row items-center shrink-0 space-x-16">
          <text class="font_2 text_4">30</text>
          <view class="flex-row items-center shrink-0 space-x-4">
            <image
              class="shrink-0 image"
              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385889258153171.png"
            />
            <text class="font_2 text_5">30</text>
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
		    swiperStyle: {
		        width: '750rpx', // 设置轮播图的宽度
		        height: '1000rpx', // 设置轮播图的高度
		        },
		        imageList: [
		          '../../static/gou4.png',
		          '../../static/gou5.png',
		          '../../static/gou6.png'
		        ]

	  };
    },

    methods: {
		change(){
			this.status=!this.status
		}
	},
  };
</script>

<style scoped lang="scss">
	.swiper-container {
	  width: 100%;
	  height: 100%;
	  display: flex;
	  align-items: center;
	  justify-content: center;
	}
	
	.my-swiper {
	  width: 100%;
	  height: 100%;
	}
	.da{
		width: 750rpx;
		height:1000rpx;
	}
	.guanzhued{
		line-height: 42rpx;
		text-align: center;
		width: 110rpx;
		border-radius: 40rpx;
		border: 1px solid #7e8183;
	}
	.guanzhu{
		line-height: 42rpx;
		text-align: center;
		width: 110rpx;
		border-radius: 40rpx;
		border: 1px solid #ff0000;
	}
	.font_22 {
		
	  font-size: 20rpx;
	  font-family: SegoeUI-Bold;
	  // line-height: 10rpx;
	  font-weight: 700;
	  color: red;
	padding-bottom: 5rpx;
	}
	.font_23 {
		
	  font-size: 20rpx;
	  font-family: SegoeUI-Bold;
	  // line-height: 10rpx;
	  font-weight: 700;
	  color: #6f7173;
	padding-bottom: 5rpx;
	}
	.tupian{
		width: 750rpx;
		height: 1000rpx;
	}
	.tupian2{
		margin-top: 5rpx;
		width: 45rpx;
		height: 45rpx;
	}
  .page {
    background-color: #edeff1;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .section {
      padding: 24rpx 30rpx 16rpx;
      background-color: #ffffff;
      .section_2 {
        background-color: #989898;
        border-radius: 50%;
        width: 82rpx;
        height: 82rpx;
      }
      .text {
        line-height: 33rpx;
		margin-right: 240rpx;
      }
    }
    .space-x-14 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-left: 28rpx;
      }
    }
    .section_3 {
      padding: 40rpx 36rpx 16rpx;
      background-color: #ffffff;
      .group {
        width: 552rpx;
        height: 319rpx;
        .text_2 {
          color: #202020;
          line-height: 52rpx;
        }
        .text-wrapper {
          margin-top: -16rpx;
          padding: 16rpx 0;
          background-color: #65cbc8;
          border-radius: 40rpx;
          .text_3 {
            margin: 0 24rpx;
            color: #ffffff;
            line-height: 30rpx;
          }
        }
      }
      .group_2 {
        padding-left: 4rpx;
        .space-x-7 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-left: 14rpx;
          }
          .section_4 {
            background-color: #ebebeb;
            border-radius: 50%;
            width: 90rpx;
            height: 90rpx;
          }
          .text-wrapper_2 {
            padding: 24rpx 0 12rpx;
            background-color: #f3f4ff;
            border-radius: 24rpx;
            height: 64rpx;
            .text_6 {
              margin-left: 20rpx;
              color: #78708c;
              line-height: 29rpx;
            }
          }
        }
        .space-x-16 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-left: 32rpx;
          }
          .text_4 {
            font-size: 42rpx;
          }
          .space-x-4 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 8rpx;
            }
            .image {
              width: 54rpx;
              height: 50rpx;
            }
            .text_5 {
              line-height: 32rpx;
            }
          }
        }
      }
      .space-x-20 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 40rpx;
        }
      }
      .font_3 {
        font-size: 32rpx;
        font-family: SegoeUI-Bold;
        line-height: 31rpx;
        font-weight: 700;
      }
      .font_2 {
        font-size: 44rpx;
        font-family: SegoeUI-Bold;
        line-height: 31rpx;
        font-weight: 700;
        color: #707070;
      }
    }
    .space-y-102 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 0rpx;
      }
    }
    .font_1 {
      font-size: 36rpx;
      font-family: SegoeUI-Bold;
      line-height: 44rpx;
      font-weight: 700;
      color: #202020;
    }
  }
  .space-y-416 {
    & > view:not(:first-child),
    & > text:not(:first-child),
    & > image:not(:first-child) {
      // margin-top: 100rpx;
    }
  }
</style>