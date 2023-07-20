<template>
	<view class="flex-col page">
	  
	  <view class="flex-row justify-between items-center section">
	    <!-- <view class="flex-col justify-start items-center text-wrapper"><text class="font_1">0</text></view> -->
	    <view class="flex-col justify-start items-center text-wrapper"><text class="font_1 text_2">{{dateFormat1(date)}}</text></view>
	    <text class="font_2 text_3">月</text>
	    <!-- <view class="flex-col justify-start items-center text-wrapper"><text class="font_1">0</text></view> -->
	    <view class="flex-col justify-start items-center text-wrapper " ><text class="font_1 ">{{dateFormat2(date)}}</text></view>
	    <text class="font_2 text_4">日</text>
	    <!-- <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_1">1</text></view> -->
	    <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_1">{{dateFormat3(date)}}</text></view>
	    <text class="font_2 text_5">时</text>
	    <!-- <view class="flex-col justify-start items-center text-wrapper"><text class="font_1">3</text></view> -->
	    <view class="flex-col justify-start items-center text-wrapper"><text class="font_1">{{dateFormat4(date)}}</text></view>
	    <text class="font_2 text_6">分</text>
	  </view>
	  <view class="flex-col justify-start relative text-wrapper_3">
	    <text class="font_3 text_7">我想你发烫的手机需要冷静一下~</text>
	  </view>
	  <view class="flex-col group space-y-12">
	    <view class="flex-col justify-start text-wrapper_4"><text class="text_8">做人嘛，开心最重要啦~</text></view>
	    <image
	      class="self-center image"
	      src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385922564373491.png"
	    />
	  </view>
	  <view class="flex-row items-center self-center section_2 space-x-2">
	    <view class="section_3"></view>
	    <text class="font_2 text_9">换个心情</text>
	  </view>
	  <view class="flex-row group_2 space-x-8">
	    <view class="flex-col justify-start items-center flex-auto text-wrapper_5">
	      <text class="font_3 text_11">随手记录心情吧~</text>
	    </view>
	    <view class="flex-col justify-start items-center shrink-0 text-wrapper_6">
	      <text class="font_3 text_10">快速记录</text>
	    </view>
	  </view>
	</view>
</template>

<script>
	export default{
		data(){		
			return{
				date: new Date().toISOString(),	
			}
		},
		onLoad(){	
			let _this = this;
			setInterval(function() {
			_this.date = Date.parse(new Date());
			}, 1000);
		},
		methods:{	
			dateFormat1(time) {
				let date = new Date(time);
				let year = date.getFullYear();
				// 在日期格式中，月份是从0开始的，因此要加0，使用三元表达式在小于10的前面加0，以达到格式统一  如 09:11:05
				let month = date.getMonth() + 1 < 10 ? "0" + (date.getMonth() + 1) : date.getMonth() + 1;
				let day = date.getDate() < 10 ? "0" + date.getDate() : date.getDate();
				let hours = date.getHours() < 10 ? "0" + date.getHours() : date.getHours();
				let minutes = date.getMinutes() < 10 ? "0" + date.getMinutes() : date.getMinutes();
				let seconds = date.getSeconds() < 10 ? "0" + date.getSeconds() : date.getSeconds();
				// 拼接
				return month
				// return year + "-" + month + "-" + day;
			},
			dateFormat2(time) {
				let date = new Date(time);
				let year = date.getFullYear();
				// 在日期格式中，月份是从0开始的，因此要加0，使用三元表达式在小于10的前面加0，以达到格式统一  如 09:11:05
				let month = date.getMonth() + 1 < 10 ? "0" + (date.getMonth() + 1) : date.getMonth() + 1;
				let day = date.getDate() < 10 ? "0" + date.getDate() : date.getDate();
				let hours = date.getHours() < 10 ? "0" + date.getHours() : date.getHours();
				let minutes = date.getMinutes() < 10 ? "0" + date.getMinutes() : date.getMinutes();
				let seconds = date.getSeconds() < 10 ? "0" + date.getSeconds() : date.getSeconds();
				// 拼接
				return  day;
				// return year + "-" + month + "-" + day;
			},
			dateFormat3(time) {
				let date = new Date(time);
				let year = date.getFullYear();
				// 在日期格式中，月份是从0开始的，因此要加0，使用三元表达式在小于10的前面加0，以达到格式统一  如 09:11:05
				let month = date.getMonth() + 1 < 10 ? "0" + (date.getMonth() + 1) : date.getMonth() + 1;
				let day = date.getDate() < 10 ? "0" + date.getDate() : date.getDate();
				let hours = date.getHours() < 10 ? "0" + date.getHours() : date.getHours();
				let minutes = date.getMinutes() < 10 ? "0" + date.getMinutes() : date.getMinutes();
				let seconds = date.getSeconds() < 10 ? "0" + date.getSeconds() : date.getSeconds();
				// 拼接
				return  hours ;
				// return year + "-" + month + "-" + day;
			},
			dateFormat4(time) {
				let date = new Date(time);
				let year = date.getFullYear();
				// 在日期格式中，月份是从0开始的，因此要加0，使用三元表达式在小于10的前面加0，以达到格式统一  如 09:11:05
				let month = date.getMonth() + 1 < 10 ? "0" + (date.getMonth() + 1) : date.getMonth() + 1;
				let day = date.getDate() < 10 ? "0" + date.getDate() : date.getDate();
				let hours = date.getHours() < 10 ? "0" + date.getHours() : date.getHours();
				let minutes = date.getMinutes() < 10 ? "0" + date.getMinutes() : date.getMinutes();
				let seconds = date.getSeconds() < 10 ? "0" + date.getSeconds() : date.getSeconds();
				// 拼接
				return seconds;
				// return year + "-" + month + "-" + day;
			}
		}
	}
</script>


<style scoped lang="scss">
.page {
    padding: 44rpx 32rpx 62rpx;
    background-image: linear-gradient(180deg, #bdf5f0 0%, #f2f2e8 26.4%, #e8f5f4 51.1%, #59d5d3 100%);
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
	position: fixed;
    .section {
      margin: 52rpx 8rpx 0;
      padding: 16rpx 32rpx;
      background-color: #7bdddb;
      border-radius: 24rpx;
      .text-wrapper {
        padding: 16rpx 0;
        background-color: #ffffff;
        border-radius: 24rpx;
        width: 46rpx;
        height: 64rpx;
        .text_2 {
          line-height: 28rpx;
        }
      }
      .text_3 {
        font-size: 36rpx;
        line-height: 31rpx;
      }
      .text_4 {
        font-size: 36rpx;
        line-height: 30rpx;
      }
      .text-wrapper_2 {
        padding: 16rpx 0;
        background-color: #ffffff;
        border-radius: 24rpx;
        width: 48rpx;
        height: 64rpx;
      }
      .font_1 {
        font-size: 38rpx;
        font-family: SegoeUI-Bold;
        line-height: 29rpx;
        font-weight: 700;
        color: #59a09e;
		
      }
      .text_5 {
        line-height: 31rpx;
      }
      .text_6 {
        line-height: 31rpx;
      }
    }
    .text-wrapper_3 {
      margin-right: 16rpx;
      margin-top: 52rpx;
      padding: 48rpx 0 28rpx;
      background-color: #ffffff;
      border-radius: 60rpx;
      box-shadow: 0px 6rpx 12rpx #a1a1a129;
      .text_7 {
        margin-left: 44rpx;
        margin-right: 32rpx;
        color: #51c5c3;
      }
    }
    .group {
      padding: 96rpx 78rpx;
      .text-wrapper_4 {
        padding: 52rpx 0 92rpx;
        background-image: url('https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385923714170159.png');
        background-size: 100% 100%;
        background-repeat: no-repeat;
        .text_8 {
          margin-left: 32rpx;
          margin-right: 16rpx;
          color: #343434;
          font-size: 44rpx;
          font-family: SegoeUI-Bold;
          font-weight: 700;
          line-height: 42rpx;
		  text-align: center;
        }
      }
      .image {
        width: 350rpx;
        height: 350rpx;
      }
    }
    .space-y-12 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 24rpx;
      }
    }
    .section_2 {
      margin-top: 6rpx;
      padding: 4rpx 16rpx 10rpx;
      background-color: #ffffff4d;
      border-radius: 60rpx;
      .section_3 {
        background-color: #00000000;
        width: 72rpx;
        height: 72rpx;
      }
      .text_9 {
        margin-right: 36rpx;
        font-size: 32rpx;
        line-height: 30rpx;
		
      }
    }
    .space-x-2 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-left: 4rpx;
      }
    }
    .font_2 {
      font-size: 34rpx;
      font-family: SegoeUI-Bold;
      line-height: 29rpx;
      font-weight: 700;
      color: #ffffff;
	  padding-right: 25rpx;
    }
    .group_2 {
      margin-top: 224rpx;
      padding: 0 8rpx;
      .text-wrapper_5 {
        padding: 44rpx 0 20rpx;
        border-radius: 60rpx;
        height: 102rpx;
        .text_11 {
          color: #ffffff;
        }
      }
      .text-wrapper_6 {
        padding: 32rpx 0;
        background-color: #ffffff;
        border-radius: 60rpx;
        width: 230rpx;
        height: 102rpx;
        .text_10 {
          color: #7bdddb;
        }
      }
    }
    .space-x-8 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-left: 16rpx;
      }
    }
    .font_3 {
      font-size: 40rpx;
      font-family: SegoeUI-Bold;
      line-height: 37rpx;
      font-weight: 700;
	  text-align: center;
    }
	
  }
</style>
