<template>
	<view class="flex-col page">
		<view class="status_bar">
		    <!-- 这里是状态栏 -->
		</view>
	  <view class="flex-col items-start group space-y-18">
	    <text class="text">HELLO!</text>
	    <text class="text_2">欢迎来到灵犀知心</text>
	  </view>
	  <view class="flex-col section">
	    <view class="flex-row justify-evenly items-center section_2">
	      <text class="font_1">短信登录</text>
	      <view class="flex-col justify-start items-center relative text-wrapper">
	        <text class="font_1">账号登录</text>
	      </view>
	      <text class="font_1">账号注册</text>
	    </view>
	    <view class="flex-col group_2 space-y-8">
	      <text class="self-start font_2">账号</text>
	      <input class="flex-col justify-start items-start text-wrapper_2" placeholder="  输入用户名/手机号/邮箱" placeholder-style="font-size: 29rpx">
	        <!-- -<text class="font_3 text_3">输入用户名/手机号/邮箱</text> -->
	      </input>
	    </view>
	    <view class="flex-col group_2 space-y-16">
	      <view class="flex-col space-y-4">
	        <text class="self-start font_2 text_4">密码</text>
	        <input type="password" class="flex-col justify-start items-start text-wrapper_3" placeholder="  输入密码（6-12个数字或字母）" placeholder-style="font-size: 29rpx">
	        </input>
	      </view>
	      <text class="self-end font_3 text_6">忘记密码</text>
	    </view>
	    <view class="flex-col justify-start items-center self-center text-wrapper_4">
	      <text class="text_7" @click="goliaojie">登录</text>
	    </view>
	    <view class="flex-col group_3 space-y-20">
	      <view class="flex-col space-y-8">
	        <text class="self-center font_3 text_8">第三方登录</text>
	        <view class="flex-row justify-between">
	          <view class="section_3"></view>
	          <view class="section_3"></view>
	          <view class="section_3 view"></view>
	        </view>
	      </view>
	      <view class="flex-row items-center group_4 space-x-2">
	        <view class="shrink-0 section_4"></view>
	        <text class="text_9">已阅读并同意《用户协议》和《隐私协议》</text>
	      </view>
	    </view>
	  </view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {
			goliaojie(){
				uni.navigateTo({
					url:'/pages/liaojie/liaojie'
				})
			}

		}
	}
</script>

<style scoped lang="scss">
	.page {
	  padding-top: 84rpx;
	  position: fixed;
	  //bottom: 0;
	  background-image: linear-gradient(180deg, #ccf0f0 0%, #ebedff 51.2%, #ccf0f0 100%);
	  width: 100%;
	  overflow-y: auto;
	  overflow-x: hidden;
	  height: 100%;
	  .group {
	    padding: 0 52rpx;
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
	  .space-y-18 {
	    & > view:not(:first-child),
	    & > text:not(:first-child),
	    & > image:not(:first-child) {
	      margin-top: 36rpx;
	    }
	  }
	  .section {
		  // position: fixed;
		  // bottom: 0;
	    margin: 328rpx 40rpx 0;
	    padding: 48rpx 32rpx 0;
	    background-color: #ffffff;
	    border-radius: 40rpx 40rpx 0 0;
	    .section_2 {
	      padding: 4rpx 40rpx;
	      background-color: #eaeaea;
	      border-radius: 40rpx;
	      box-shadow: 0px 6rpx 12rpx #00000029;
	      .font_1 {
	        font-size: 36rpx;
	        font-family: SegoeUI-Bold;
	        line-height: 33rpx;
	        font-weight: 700;
	        color: #202020;
	      }
	      .text-wrapper {
	        padding: 24rpx 0;
	        background-color: #ffffff;
	        border-radius: 40rpx;
	        box-shadow: 0px 6rpx 12rpx #00000029;
	        width: 214rpx;
	        height: 84rpx;
	      }
	    }
	    .group_2 {
	      margin-top: 72rpx;
	      padding: 0 36rpx;
	      .font_2 {
	        font-size: 44rpx;
	        font-family: SegoeUI;
	        line-height: 40rpx;
	        color: #202020;
	      }
	      .text-wrapper_2 {
			// height: 20rpx;
			// min-height:1rem;

	        padding: 32rpx 0;
	        background-color: #f2f2f2;
	        border-radius: 16rpx;
	        .text_3 {
	          margin-left: 20rpx;
	        }
	      }
	      .space-y-4 {
	        & > view:not(:first-child),
	        & > text:not(:first-child),
	        & > image:not(:first-child) {
	          margin-top: 8rpx;
	        }
	        .text_4 {
	          line-height: 41rpx;
	        }
	        .text-wrapper_3 {
	          padding: 28rpx 0;
	          background-color: #f2f2f2;
	          border-radius: 16rpx;
	          .text_5 {
	            margin-left: 20rpx;
	            line-height: 27rpx;
	          }
	        }
	      }
	      .text_6 {
	        margin-right: 4rpx;
	        color: #202020;
	      }
	    }
	    .space-y-8 {
	      & > view:not(:first-child),
	      & > text:not(:first-child),
	      & > image:not(:first-child) {
	        margin-top: 16rpx;
	      }
	      .text_8 {
	        color: #d5d5d5;
	      }
	      .section_3 {
	        background-color: #00000000;
	        width: 82rpx;
	        height: 82rpx;
	      }
	      .view {
	        margin-right: 16rpx;
	      }
	    }
	    .space-y-16 {
	      & > view:not(:first-child),
	      & > text:not(:first-child),
	      & > image:not(:first-child) {
	        margin-top: 32rpx;
	      }
	    }
	    .text-wrapper_4 {
	      margin-top: 64rpx;
	      padding: 32rpx 0 28rpx;
	      background-color: #65cbc8;
	      border-radius: 48rpx;
	      width: 476rpx;
	      .text_7 {
	        color: #f6f6f6;
	        font-size: 44rpx;
	        font-family: SegoeUI-Bold;
	        font-weight: 700;
	        line-height: 40rpx;
	      }
	    }
	    .group_3 {
	      padding: 64rpx 60rpx 40rpx;
	      .group_4 {
	        padding-left: 68rpx;
	        .section_4 {
	          background-color: #ffffff66;
	          border-radius: 8rpx;
	          width: 28rpx;
	          height: 28rpx;
	        }
	        .text_9 {
	          color: #b8b8b8;
	          font-size: 20rpx;
	          font-family: SegoeUI;
	          line-height: 19rpx;
	        }
	      }
	      .space-x-2 {
	        & > view:not(:first-child),
	        & > text:not(:first-child),
	        & > image:not(:first-child) {
	          margin-left: 4rpx;
	        }
	      }
	    }
	    .space-y-20 {
	      & > view:not(:first-child),
	      & > text:not(:first-child),
	      & > image:not(:first-child) {
	        margin-top: 40rpx;
	      }
	    }
	    .font_3 {
	      font-size: 28rpx;
	      font-family: SegoeUI;
	      line-height: 26rpx;
	      color: #b1b1b1;
	    }
	  }
	}
</style>
