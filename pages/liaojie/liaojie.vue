<template>
	<view class="flex-col page">
		<view class="status_bar">
		    <!-- 这里是状态栏 -->
		</view>
	  <view class="flex-col items-start space-y-18">
	    <text class="text">HELLO!</text>
	    <text class="text_2">欢迎来到灵犀知心</text>
	  </view>
	  <view class="flex-col items-start group space-y-6">
	    <text class="font_1">在进入首页前，</text>
	    <text class="font_1">我们想了解您的一些信息。</text>
	  </view>
	  <view class="flex-col items-center group_2 space-y-6">
	    <view class="flex-col justify-start items-center text-wrapper" @click="gowanshanziliao"><text class="font_1 text_3">下一页</text></view>
	    <text class="text_4"@click="goshouye">跳 过</text>
	  </view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods:{
			goshouye(){
				uni.switchTab({
					url:'/pages/shouye/shouye'
				})
			},
			gowanshanziliao(){
				uni.navigateTo({
					url:'/pages/wanshanziliao/wanshanziliao'
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
.page {
    padding: 84rpx 40rpx 120rpx;
    background-image: linear-gradient(180deg, #ccf0f0 0%, #ebedff 50.9%, #ccf0f0 100%);
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
	position: fixed;
			// top: 0;
			// left: 0;
			// right: 0;
			// bottom: 0;
			//z-index: -1;
	
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
    .group {
      margin-top: 536rpx;
      padding-left: 44rpx;
      padding-right: 32rpx;
    }
    .space-y-6 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 12rpx;
      }
    }
    .group_2 {
      margin-top: 480rpx;
      .text-wrapper {
        padding: 32rpx 0 24rpx;
        background-color: #65cbc8;
        border-radius: 60rpx;
        width: 308rpx;
        .text_3 {
			color: #f6f6f6;
			line-height: 42rpx;
			font-size: 44rpx;
        }
      }
      .text_4 {
        color: #b6c5c5;
        font-size: 36rpx;
        font-family: SegoeUI-Bold;
        font-weight: 700;
        line-height: 33rpx;
      }
    }
    .font_1 {
      font-size: 48rpx;
      font-family: SegoeUI-Bold;
      line-height: 58rpx;
      font-weight: 700;
      color: #202020;
    }
  }
</style>
