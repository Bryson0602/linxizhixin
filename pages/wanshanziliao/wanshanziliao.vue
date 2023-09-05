<template>
	<view class="flex-col page">
		<view class="status_bar">
		    <!-- 这里是状态栏 -->
		</view>
	  <view class="flex-col items-start space-y-18">
	    <text class="text">HELLO!</text>
	    <text class="text_2">欢迎来到灵犀知心</text>
	  </view>
	  <text class="self-start font_1 text_3">请您完善一下个人资料</text>
	  <view class="flex-col group">
	    <text class="self-start font_2">性别</text>
	    <view class="flex-row self-center">
	      <view class="flex-col equal-division-item space-y-8" @click="selectGender('男生')" >
	        <view class="section" :class="{ 'selected': gender === '男生' }">
				<image src="../../static/boy.png" mode=""></image>
			</view>
	        <text class="self-center font_2">男生</text>
	        <view class="self-center group_2"></view>
	      </view>
	      <view class="flex-col equal-division-item space-y-8" @click="selectGender('女生')">
	        <view class="section" :class="{ 'selected': gender === '女生' }">
				<image src="../../static/girl.png" mode=""></image>
			</view>
	        <text class="self-center font_2">女生</text>
	        <view class="self-center group_2"></view>
	      </view>
	    </view>
	  </view>
	  <text class="self-start font_2 text_4">出生时间</text>
	  <view class="flex-row justify-evenly items-center group_3">
	    <picker class="section_2" @change="bindPickerChange" :value="index" :range="array">
			<view class="uni-input">{{array[index]}}</view>
		</picker>
	    <text class="font_2">年</text>
	    <picker class="section_3" @change="bindPickerChange1" :value="index1" :range="array1">
	    	<view class="uni-input1">{{array1[index1]}}</view>
	    </picker>
	    <text class="font_2 text_5">月</text>
	    <picker class="section_3" @change="bindPickerChange2" :value="index2" :range="array2">
	    	<view class="uni-input1">{{array2[index2]}}</view>
	    </picker>
	    <text class="font_2 text_6">日</text>
	  </view>
	  <text class="self-start font_2 text_7">所在学校</text>
	  <input class="self-center section_4"></input>
	  <view class="flex-col items-center group_4 space-y-6">
	    <view class="flex-col justify-start items-center text-wrapper" @click="gombti"><text class="font_1 text_8">下一页</text></view>
	    <text class="font_2 text_9" @click="goshouye">跳 过</text>
	  </view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				gender:"男生",
				array: ['1990', '1991', '1992', '1993', '1994', '1995', '1996', '1997', '1998', '1999', '2000', '2001', '2002', '2003', '2004', '2005', '2006', '2007', '2008', '2009', '2010'],
				index: 0,
				array1: ['1', '2', '3', '4','5', '6', '7', '8','9', '10', '11', '12'],
				index1: 0,
				array2: ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10', '11', '12', '13', '14', '15', '16', '17', '18', '19', '20', '21', '22', '23', '24', '25', '26', '27', '28', '29', '30', '31'],
				index2: 0,
			};
		},
		methods:{
			goshouye(){
				uni.switchTab({
					url:'/pages/shouye/shouye'
				})
			},
			selectGender(value) { // 添加selectGender方法来设置gender变量的值
			      this.gender = value;
			},
			bindPickerChange: function(e) {
				console.log('picker发送选择改变，携带值为', e.detail.value)
				this.index = e.detail.value
			},
			bindPickerChange1: function(e) {
				console.log('picker发送选择改变，携带值为', e.detail.value)
				this.index1 = e.detail.value
			},
			bindPickerChange2: function(e) {
				console.log('picker发送选择改变，携带值为', e.detail.value)
				this.index2 = e.detail.value
			},
			gombti(){
				uni.navigateTo({
					url:'/pages/mbti/mbti'
				})
			}
		}
	}
</script>

<style scoped lang="scss">
.page {
    padding: 84rpx 52rpx 40rpx;
    background-image: linear-gradient(180deg, #ccf0f0 0%, #ebedff 50.5%, #ebedff 51.5%, #ccf0f0 100%);
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
	position: fixed;
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
      font-weight: 700;
      color: #202020;
    }
    .text_3 {
      margin-left: 12rpx;
      margin-top: 164rpx;
      line-height: 45rpx;
    }
    .group {
      margin-top: 56rpx;
      padding: 0 12rpx;
      .equal-division-item {
        flex: 1 1 248rpx;
        padding: 8rpx 48rpx;
        width: 248rpx;
        .section {
          background-color: #ffffff;
          border-radius: 50%;
          height: 156rpx;
		  width: 156rpx;
		  overflow: hidden;
		  image{
			  height: 156rpx;
			  width: 156rpx; 
		  }
        }
		.selected{
		    border: 8rpx solid #af9ef3; /* 添加蓝色边框样式 */
		}
        .group_2 {
          border-radius: 50%;
          width: 26rpx;
          height: 26rpx;
        }
      }
      .space-y-8 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 16rpx;
        }
      }
    }
    .font_2 {
      font-size: 36rpx;
      font-family: SegoeUI-Bold;
      line-height: 33rpx;
      font-weight: 700;
      color: #202020;
    }
    .text_4 {
      margin-left: 16rpx;
      margin-top: 52rpx;
	  
      color: #434343;
    }
    .group_3 {
      margin-top: 48rpx;
      padding: 0 48rpx;
      .section_2 {
        background-color: #ffffff;
        border-radius: 60rpx;
        width: 180rpx;
        height: 70rpx;
		.uni-input{
			text-align: center;
			line-height: 70rpx;
		}
      }
      .section_3 {
        background-color: #ffffff;
        border-radius: 60rpx;
        width: 96rpx;
        height: 70rpx;
		.uni-input1{
			text-align: center;
			line-height: 70rpx;
		}
      }
      .text_5 {
        line-height: 31rpx;
      }
      .text_6 {
        line-height: 30rpx;
      }
    }
    .text_7 {
      margin-left: 12rpx;
      margin-top: 112rpx;
      line-height: 34rpx;
    }
    .section_4 {
      margin-top: 60rpx;
	  padding: 20rpx 0;
      background-color: #ffffff;
      border-radius: 60rpx;
      width: 400rpx;
      height: 70rpx;
	  text-align: center;
    }
    .group_4 {
      padding: 96rpx 0;
      .text-wrapper {
        padding: 32rpx 0 24rpx;
        background-color: #65cbc8;
        border-radius: 60rpx;
        width: 308rpx;
        .text_8 {
          color: #f6f6f6;
          line-height: 42rpx;
          font-size: 44rpx;
        }
      }
      .text_9 {
        color: #b6c5c5;
		 line-height: 63rpx;
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
