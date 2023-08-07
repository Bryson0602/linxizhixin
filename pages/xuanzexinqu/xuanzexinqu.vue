<template>
	<view class="flex-col page space-y-106">
		<view class="status_bar">
		    <!-- 这里是状态栏 -->
		</view>
	  <view class="flex-col items-start group space-y-18">
	    <text class="text">HELLO!</text>
	    <text class="text_2">欢迎来到灵犀知心</text>
	  </view>
	  <view class="flex-col group_2">
	    <text class="self-start font_1">您主要想了解的模块是？</text>
	    <view class="flex-col group_3 space-y-18">
	      <view class="flex-row space-x-14">
	        <view class="flex-col justify-start items-center relative text-wrapper " @click="toggleBg('module1')" v-bind:style="{backgroundColor: bgColors.module1}">
	          <text class="font_2">抑郁</text>
	        </view>
	        <view class="flex-col justify-start items-center relative text-wrapper " @click="toggleBg('module2')" v-bind:style="{backgroundColor: bgColors.module2}">
	          <text class="font_2">焦虑</text>
	        </view>
	        <view class="flex-col justify-start items-center text-wrapper " @click="toggleBg('module3')" v-bind:style="{backgroundColor: bgColors.module3}"><text class="font_2">恐慌</text></view>
	      </view>
	      <view class="flex-row space-x-14">
	        <view class="flex-col justify-start items-center relative text-wrapper_2" @click="toggleBg('module4')" v-bind:style="{backgroundColor: bgColors.module4}">
	          <text class="font_2">自闭</text>
	        </view>
	        <view class="flex-col justify-start items-center relative text-wrapper_2" @click="toggleBg('module5')" v-bind:style="{backgroundColor: bgColors.module5}">
	          <text class="font_2">沮丧</text>
	        </view>
	        <view class="flex-col justify-start items-center text-wrapper_2" @click="toggleBg('module6')" v-bind:style="{backgroundColor: bgColors.module6}"><text class="font_2">疲惫</text></view>
	      </view>
	      <view class="flex-row space-x-14">
	        <view class="flex-col justify-start items-center relative text-wrapper_3" @click="toggleBg('module7')" v-bind:style="{backgroundColor: bgColors.module7}">
	          <text class="font_3 text_3">开学焦虑</text>
	        </view>
	        <view class="flex-col justify-start items-center relative text-wrapper_3"  @click="toggleBg('module8')" v-bind:style="{backgroundColor: bgColors.module8}">
	          <text class="font_3">注意障碍</text>
	        </view>
	        <view class="flex-col justify-start items-center text-wrapper_3" @click="toggleBg('module9')" v-bind:style="{backgroundColor: bgColors.module9}"><text class="font_3">人格障碍</text></view>
	      </view>
	    </view>
	    <view class="flex-col group_4 space-y-23">
	      <view class="flex-row space-x-14">
	        <view class="flex-col justify-start items-center relative text-wrapper_4" @click="toggleBg('module10')" v-bind:style="{backgroundColor: bgColors.module10}">
	          <text class="font_3">心理保健</text>
	        </view>
	        <view class="flex-col justify-start items-center relative text-wrapper_4" @click="toggleBg('module11')" v-bind:style="{backgroundColor: bgColors.module11}">
	          <text class="font_3">学习逃避</text>
	        </view>
	        <view class="flex-col justify-start items-center text-wrapper_4" @click="toggleBg('module12')" v-bind:style="{backgroundColor: bgColors.module12}"><text class="font_3">成就压力</text></view>
	      </view>
	      <view class="flex-row space-x-14">
	        <view class="flex-col justify-start items-center relative text-wrapper_3" @click="toggleBg('module13')" v-bind:style="{backgroundColor: bgColors.module13}">
	          <text class="text_4">提升幸福感</text>
	        </view>
	        <view class="flex-col justify-start items-center relative text-wrapper_3" @click="toggleBg('module14')" v-bind:style="{backgroundColor: bgColors.module14}">
	          <text class="font_3">恋爱挫折</text>
	        </view>
	        <view class="flex-col justify-start items-center text-wrapper_3" @click="toggleBg('module15')" v-bind:style="{backgroundColor: bgColors.module15}">
	          <text class="font_3 text_5">家庭挫折</text>
	        </view>
	      </view>
	    </view>
	    
	    <view class="flex-col group_5 space-y-6">
	      <view class="flex-col justify-start items-center text-wrapper_5" @click="goshouye"><text class="font_1 text_7">完成</text></view>
	      <text class="self-center font_4 text_8"@click="goshouye">跳 过</text>
	    </view>
	  </view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				bgColors: {
				  module1: '#ffffff',
				  module2: '#ffffff',
				  module3: '#ffffff' ,
				  module4: '#ffffff' ,
				  module5: '#ffffff' ,
				  module6: '#ffffff' ,
				  module7: '#ffffff' ,
				  module8: '#ffffff' ,
				  module9: '#ffffff' ,
				  module10: '#ffffff' ,
				  module11: '#ffffff' ,
				  module12: '#ffffff' ,
				  module13: '#ffffff' ,
				  module14: '#ffffff' ,
				  module15: '#ffffff' 
				}
			};
		},
		methods: {
		  toggleBg(module) {
			if(this.bgColors[module] === '#ffffff') {
			  this.bgColors[module] = '#fadeff';
			} else {
			  this.bgColors[module] = '#ffffff';
			}
		  },goshouye(){
				uni.switchTab({
					url:'/pages/shouye/shouye',
				})
			}
		}
	}
</script>

<style scoped lang="scss">
.page {
	
	position: fixed;
    padding: 0rpx 0 120rpx;
    background-image: linear-gradient(180deg, #ccf0f0 0%, #ebedff 50.9%, #ccf0f0 100%);
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
    .group_2 {
      padding: 150rpx 66rpx;
      .font_1 {
        font-size: 48rpx;
        font-family: SegoeUI-Bold;
        line-height: 44rpx;
        font-weight: 700;
        color: #202020;
      }
      .group_3 {
        margin-top: 100rpx;
      }
      .group_4 {
        margin-top: 46rpx;
      }
      .space-y-23 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 46rpx;
        }
      }
      .space-x-14 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 28rpx;
        }
        .text-wrapper {
          flex: 1 1 188rpx;
          padding: 24rpx 0;
          background-color: #ffffff;
          border-radius: 60rpx;
          box-shadow: 0px 6rpx 12rpx #00000029;
          height: 88rpx;
        }
		// .c1{
		// 	background-color: #73e8e5;
		// }
		// .c2{
		// 	background-color: #73e8e5;
		// }
		// .c3{
		// 	background-color: #73e8e5;
		// }
        .text-wrapper_2 {
          flex: 1 1 188rpx;
          padding: 28rpx 0 20rpx;
          background-color: #ffffff;
          border-radius: 60rpx;
          box-shadow: 0px 6rpx 12rpx #00000029;
          height: 88rpx;
        }
        .font_2 {
          font-size: 40rpx;
          font-family: SegoeUI;
          line-height: 37rpx;
          color: #202020;
        }
        .text-wrapper_3 {
          flex: 1 1 188rpx;
          padding: 28rpx 0;
          background-color: #ffffff;
          border-radius: 60rpx;
          box-shadow: 0px 6rpx 12rpx #00000029;
          height: 88rpx;
          .text_3 {
            line-height: 34rpx;
          }
          .text_4 {
            color: #202020;
            font-size: 32rpx;
            font-family: SegoeUI;
            line-height: 30rpx;
          }
          .text_5 {
            line-height: 34rpx;
          }
        }
        .text-wrapper_4 {
          flex: 1 1 188rpx;
          padding: 28rpx 0;
          background-color: #ffffff;
          border-radius: 60rpx;
          box-shadow: 0px 6rpx 12rpx #00000029;
          height: 86rpx;
        }
        .font_3 {
          font-size: 36rpx;
          font-family: SegoeUI;
          line-height: 33rpx;
          color: #202020;
        }
      }
      .font_4 {
        font-size: 36rpx;
        font-family: SegoeUI-Bold;
        line-height: 33rpx;
        font-weight: 700;
      }
      .text_6 {
        margin-left: 8rpx;
        margin-top: 60rpx;
        color: #202020;
      }
      .group_5 {
        margin-top: 124rpx;
        padding: 0 154rpx;
        .text-wrapper_5 {
          padding: 24rpx 0;
          background-color: #65cbc8;
          border-radius: 60rpx;
          .text_7 {
			color: #f6f6f6;
			font-size: 44rpx;
            line-height: 45rpx;
          }
        }
        .text_8 {
          color: #b6c5c5;
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
  }
  .space-y-106 {
    & > view:not(:first-child),
    & > text:not(:first-child),
    & > image:not(:first-child) {
      margin-top: 100rpx;
    }
  }
</style>
