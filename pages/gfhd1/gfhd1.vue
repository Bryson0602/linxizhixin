<template>
	<view class="flex-col page">
	  <view class="flex-col section">
	    
	    <view class="flex-col group_4 space-y-24">
	      <view class="flex-row space-x-8">
	        <view class="flex-col justify-start items-end section_3">
				<image src="../../static/lb3.jpg" mode="aspectFill"></image>
	          <view class="flex-col justify-start items-center text-wrapper_2"><text class="text_6">官方</text></view>
	        </view>
	        <text class="self-start font_1 text_5">心理知识大讲堂</text>
	      </view>
	      <view class="flex-row justify-between items-baseline">
	        <view class="group_5">
	          <text class="font_2">可报名40人</text>

	        </view>
	        <text class="font_2">已报名：18人</text>
	        <text class="font_2 text_8">已签到：2人</text>
	      </view>
	    </view>
	    <view class="flex-col group_6 space-y-12">
	      <view class="flex-row justify-between items-center">
	        <text class="font_3">报名时间</text>
	        <text class="font_4 text_9">2023.09.08-2023.09.15</text>
	      </view>
	      <view class="flex-row justify-between items-center">
	        <text class="font_3 text_10">活动时间</text>
	        <text class="font_4 text_11">2023.09.16</text>
	      </view>
	    </view>
	  </view>
	  <view class="flex-col section_4">
	    <view class=" justify-start items-start text-wrapper_3">
	      <text class="font_5 text_12">公告:</text>
		  <text class="text_16">此次活动邀请知名心理学专家带来心理健康知识讲座,内容涵盖学习心理、人际关系、情绪管理等多个方面。活动持续2个小时。</text>
	    </view>
	    <view class="flex-col group_7 space-y-20">
	      <view class="flex-row justify-between items-center group_8">
	        <view class="flex-col justify-start"><text class="text_13">信息</text></view>
	        <view class="flex-col justify-start"><text class="font_6 text_14">详情</text></view>
	        <view class="flex-col justify-start"><text class="font_6 text_15">评价</text></view>
	      </view>
	      <view class="flex-col items-start section_5 space-y-20">
	        <text class="font_7">组织者：灵犀知心</text>
	        <text class="font_7">活动地点：信息与文献中心</text>
			<text class="font_7">活动对象：全体成员</text>
			<text class="font_7">活动分类：心理素质拓展</text>
	        <text class="font_7">定位签到：不支持</text>
	        <text class="font_7">签退情况：无需签退</text>
	        <text class="font_7">联系方式：灵犀知心</text>
	      </view>
	    </view>
	  </view>
	  <view class="flex-row justify-end section_6 space-x-8-reverse">
	    <view class="flex-col justify-start items-center text-wrapper_4"><text class="font_5">打卡结果</text></view>
	    <view class="flex-col justify-start items-center text-wrapper_5" @click="toggleStatus"><text class="font_5" >{{ text }}</text></view>
	  </view>
	</view>
</template>

<script>

	export default {
		data() {
			return {
				status: false,
				text: '报名',
			};
		},
		methods: {
			toggleStatus() {
			this.status = !this.status;
			if (this.status) {
			  this.text = '已报名';
			  this.showSuccessModal(); // 调用弹窗方法
			} else {
			  this.text = '报名';  
			}
			},
			showSuccessModal() {
			  uni.showModal({
				title: '报名成功',
				content: '您已成功报名!',
				showCancel: false
			  });
			}
		}
	}
</script>

<style scoped lang="scss">
.page {
	position: fixed;
    background-color: #ebebeb;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .section {
      padding: 40rpx 40rpx 16rpx;
      background-color: #ffffff;

      .group_4 {
        margin-top: 0rpx;
        .space-x-8 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-left: 16rpx;
          }
          .section_3 {
			position: relative;
            //padding: 12rpx 0 102rpx;
            background-color: #707070;
            border-radius: 24rpx;
            width: 196rpx;
            height: 146rpx;
			overflow: hidden;
			
			image{
				width: 196rpx;
				height: 146rpx;
			}
            .text-wrapper_2 {
			  position: absolute;
			  right: 10rpx;
			  top: 10rpx;
              //margin-right: 14rpx;
              padding: 8rpx 0;
              background-color: #00aaff;
              border-radius: 60rpx;
              width: 68rpx;
              .text_6 {
                color: #ffffff;
                font-size: 20rpx;
                font-family: SegoeUI-Bold;
                font-weight: 700;
                line-height: 18rpx;
              }
            }
          }
          .text_5 {
			width: 100%;
			padding-right: 200rpx;
			line-height: 45rpx;
            margin-top: 8rpx;
            color: #202020;
          }
        }
        .group_5 {
          line-height: 26rpx;
          height: 26rpx;
          .text_7 {
            color: #707070;
            font-size: 28rpx;
            font-family: SegoeUI;
            line-height: 26rpx;
          }
        }
        .text_8 {
          margin-right: 8rpx;
        }
      }
      .space-y-24 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 48rpx;
        }
      }
      .font_1 {
        font-size: 40rpx;
        font-family: SegoeUI-Bold;
        line-height: 37rpx;
        font-weight: 700;
        color: #707070;
      }
      .font_2 {
        font-size: 28rpx;
        font-family: SegoeUI-Bold;
        line-height: 26rpx;
        font-weight: 700;
        color: #707070;
      }
      .group_6 {
        margin-top: 60rpx;
        padding-left: 68rpx;
        padding-right: 64rpx;
        .font_3 {
          font-size: 32rpx;
          font-family: SegoeUI;
          line-height: 30rpx;
          color: #707070;
        }
        .font_4 {
          font-size: 32rpx;
          font-family: SegoeUI;
          line-height: 37rpx;
          color: #000000;
        }
        .text_9 {
          line-height: 38rpx;
        }
        .text_10 {
          line-height: 29rpx;
        }
        .text_11 {
          line-height: 38rpx;
        }
      }
      .space-y-12 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 24rpx;
        }
      }
    }
    .section_4 {
      margin-top: 20rpx;
      padding: 26rpx 40rpx 0;
      background-color: #ffffff;
      height: 100%;
      .text-wrapper_3 {
        padding: 36rpx 30rpx;
        background-color: #e8f5f4;
        border-radius: 36rpx;
        .text_12 {
          margin-left: 36rpx;
		  line-height: 50rpx;
        }
		.text_16{
			margin: 0 30rpx;
			font-size: 33rpx;
			line-height: 50rpx;
		}
      }
      .group_7 {
        margin: 40rpx 0 ;
        .group_8 {
          padding-left: 108rpx;
          padding-right: 96rpx;
          .text_13 {
            color: #000000;
            font-size: 44rpx;
            font-family: SegoeUI-Bold;
            font-weight: 700;
            line-height: 41rpx;
          }
          .font_6 {
            font-size: 36rpx;
            font-family: SegoeUI;
            line-height: 33rpx;
            color: #707070;
          }
          .text_14 {
            margin: 0 8rpx;
          }
          .text_15 {
            margin: 0 8rpx;
          }
        }
        .section_5 {
          padding: 40rpx 36rpx 64rpx;
          background-color: #f3f3f3;
          border-radius: 36rpx;
          .font_7 {
            font-size: 36rpx;
            font-family: SegoeUI;
            line-height: 44rpx;
            color: #707070;
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
    }
    .section_6 {
	  position: fixed;
	  width: 100%;
	  right: 0;
	  bottom: 0;
      padding: 20rpx 40rpx;
      background-color: #badff5;
      .text-wrapper_4 {
        padding: 24rpx 0;
        background-color: #ffffff;
        border-radius: 24rpx;
        width: 248rpx;
        height: 78rpx;
      }
      .text-wrapper_5 {
        padding: 24rpx 0;
        background-color: #ffffff;
        border-radius: 24rpx;
        width: 190rpx;
        height: 78rpx;
      }
    }
    .space-x-8-reverse {
      & > view:not(:last-child),
      & > text:not(:last-child),
      & > image:not(:last-child) {
        margin-right: 16rpx;
      }
    }
    .font_5 {
      font-size: 36rpx;
      font-family: SegoeUI-Bold;
      line-height: 33rpx;
      font-weight: 700;
      color: #000000;
    }
  }
</style>
