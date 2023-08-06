<template>
	<view class="flex-col page">
		<view class="status_bar">
		    <!-- 这里是状态栏 -->
		</view>
	  <view class="flex-col items-start space-y-18">
	    <text class="text">HELLO!</text>
	    <text class="text_2">欢迎来到灵犀知心</text>
	  </view>
	  <text class="self-center font_1 text_3">您是否做过MBTI人格测试？</text>
	  <view class="self-center section">
		  <image src="../../static/lxzx-tm.png" mode="heightFix"></image>
	  </view>
	  <view class="flex-row justify-between group">
	    <view class="flex-col justify-start items-center relative text-wrapper" @click="changecolor('是')" :class="{ 'selected': yes === '是' }"><text class="font_2">是</text></view>
	    <view class="flex-col justify-start items-center text-wrapper_1" @click="changecolor('否')" :class="{ 'selected': yes === '否' }"><text class="font_2 text_4">否</text></view>
	  </view>
	  <view class="flex-col items-center group_2 space-y-6">
	    <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_1" @click="goxuanzexinqu">下一页</text></view>
	    <text class="text_5">跳 过</text>
	  </view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				yes:"",
			};
		},
		methods:{
			changecolor(value){
				this.yes = value;
			},
			goxuanzexinqu(){
				uni.navigateTo({
					url:'/pages/xuanzexinqu/xuanzexinqu'
				})
			}
		}
	}
</script>

<style scoped lang="scss">
.page {
	position: fixed;
    padding: 84rpx 48rpx 120rpx 52rpx;
    background-image: linear-gradient(180deg, #ccf0f0 0%, #ebedff 49.9%, #ccf0f0 100%);
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .space-y-18 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 36rpx;
      }
      .text {
        margin-left: 4rpx;
        color: #202020;
        font-size: 80rpx;
        font-family: SegoeUI-Bold;
        font-weight: 700;
        line-height: 58rpx;
      }
      .text_2 {
        color: #202020;
        font-size: 40rpx;
        font-family: SegoeUI-Bold;
        font-weight: 700;
        line-height: 37rpx;
      }
    }
    .font_1 {
      font-size: 48rpx;
      font-family: SegoeUI-Bold;
      line-height: 42rpx;
      font-weight: 700;
      color: #202020;
	  
    }
    .text_3 {
      margin-top: 220rpx;
      line-height: 50rpx;
    }
    .section {
      margin-top: 48rpx;
      
      width: 498rpx;
      height: 498rpx;
    }
    .group {
      margin-top: 72rpx;
      padding: 0 84rpx;
      .text-wrapper {
        padding: 20rpx 0;
        background-color: #ffffff;
        border-radius: 24rpx;
        box-shadow: 0px 6rpx 12rpx #00000029;
        width: 214rpx;
        height: 80rpx;
		
        .font_2 {
          font-size: 48rpx;
          font-family: SegoeUI;
          line-height: 42rpx;
          color: #202020;
        }
        .text_4 {
          line-height: 41rpx;
        }
      }
	  .text-wrapper_1{
		  padding: 20rpx 0;
		  background-color: #ffffff;
		  border-radius: 24rpx;
		  box-shadow: 0px 6rpx 12rpx #00000029;
		  width: 214rpx;
		  height: 80rpx;
		.font_2 {
		  font-size: 48rpx;
		  font-family: SegoeUI;
		  line-height: 42rpx;
		  color: #202020;
		}
	  }
	  .selected{
	      background-color: #95dbf8;
		  .font_2 {
		    color: #ffffff;
		  }
	  }
    }
    .group_2 {
      margin-top: 170rpx;
      .text-wrapper_2 {
        padding: 32rpx 0 24rpx;
        background-color: #65cbc8;
        border-radius: 60rpx;
        width: 308rpx;
		& .font_1{
			color: #f6f6f6;
			line-height: 42rpx;
			font-size: 44rpx;
		}
      }
      .text_5 {
        color: #b6c5c5;
        font-size: 36rpx;
        font-family: SegoeUI-Bold;
        font-weight: 700;
        line-height: 33rpx;
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
</style>
