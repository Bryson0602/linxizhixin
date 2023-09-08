<template>
  <view class="flex-col page space-y-416">
    <view class="flex-row items-center section space-x-14">
      <view class="section_2">
		  <image src="../../static/tx11.jpeg" mode="" class="section_2"></image>
	  </view>
      <text class="font_1 text">好想吃饭</text>
	  <view v-if="options.status=='true'&&status" class="guanzhu">
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
			  <swiper class="my-swiper" :style="swiperStyle" :indicator-dots="true" :autoplay="false" indicator-color=#edeff1 :duration="500" @change="swiperChange">
			    <swiper-item v-for="(item, index) in imageList" :key="index">
			    <image :src="item" mode="aspectFill" class="da"></image>
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
		  </br>
		  </br>
		  <text class="font_11">#金毛</text>
		  <text class="font_11">#我的萌宠</text>
		  <text class="font_11">#我家宠物好可爱</text>
		  </br>
		  <text class="font_44">07-08</text>
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
          <view class="flex-row items-center shrink-0 space-x-4">
			  <view v-if="status3" @click="change3" class="xin">
			  	<image
              class="shrink-0 image"
              src="../../static/aixin (1).png"
            />
			  </view>
			  <view v-else @click="change3" class="xin">
			  	<image
			  	  class="shrink-0 image"
			  	  src="../../static/aixin.png"
			  	/>
			  </view>
            
            <text class="font_28 text_5">130</text>
          </view>
          <view class="flex-row items-center shrink-0 space-x-4">
			  <view v-if="status2" @click="change2" class="xin">
			  <image
              class="shrink-0 image"
              src="../../static/shoucang.png"
            />
			    </view>
			    <view v-else @click="change2" class="xin">
			    	<image
			    	  class="shrink-0 image"
			    	  src="../../static/shoucang-xz.png"
			    	/>
			    </view>
            
            <text class="font_28 text_5">300</text>
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
		  status2:true,
		  status3:true,
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
	onLoad(options) {
		this.status=options.status
	},
    methods: {
		change(){
			this.status=!this.status
		},
		change2(){
			this.status2=!this.status2
		},
		change3(){
			this.status3=!this.status3
		},
	},
  };
</script>

<style scoped lang="scss">
	.xin{
		padding-top: 10rpx;
	}
	//设置轮播的指示点位置
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
	  /deep/ .uni-swiper-dots {
	  			// 指示点整个区域的位置
				position: absolute;
	  			bottom: 4rpx;
	  		}
	/deep/ .uni-swiper-dot {
				// 指示点元素默认样式
				width: 12upx !important;
				height: 12upx !important;
				background: #C0C0C0 !important;
			}
	
			/deep/ .uni-swiper-dot-active {
				// 指示点元素激活（当前选中）状态样式
				background: red !important;
			}
	}
	.da{
		width: 750rpx;
		height:970rpx;
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
	.font_44 {
	  font-size: 28rpx;
	  font-family: SegoeUI-Bold;
	  line-height: 18rpx;
	  font-weight: 700;
	  color: #a9a9a9;
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
    // background-color: #edeff1;
	background-color: #fff;
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
		width: 680rpx;
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
			width: 50rpx;
            .text_6 {
              margin-left: 20rpx;
              color: #78708c;
              line-height: 25rpx;
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
	  .font_28 {
	    font-size: 34rpx;
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
      font-size: 34rpx;
      font-family: SegoeUI-Bold;
      line-height: 44rpx;
      font-weight: 400;
      color: #202020;
    }
	.font_11 {
	  font-size: 34rpx;
	  font-family: SegoeUI-Bold;
	  line-height: 44rpx;
	  font-weight: 400;
	  color: rgb(36, 130, 161);
	  padding-right: 5rpx;
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