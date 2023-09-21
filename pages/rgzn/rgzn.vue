<template>
  <view class="flex-col page space-y-35">
	  <text class="font">选择你感兴趣的人工智能知识学习吧~</text>
    <view class="flex-row justify-between items-start group">
		
      <view class="flex-col justify-start items-center text-wrapper">
        <text class="font_1 text">深度学习算法</text>
      </view>
      <view class="flex-col justify-start items-center text-wrapper_2"@click="tojqxx">
        <text class="font_2 text_2">机器学习技术</text>
      </view>
    </view>
    <view class="flex-col">
      <view class="flex-row group_2">
        <view class="flex-col flex-auto space-y-33">
          <view class="flex-col justify-start items-center text-wrapper_3">
            <text class="font_2 text_4">NPL自然语言处理技术</text>
          </view>
          <view class="flex-col justify-start items-center text-wrapper_6">
            <text class="font_1 text_6">计算机视觉</text>
          </view>
        </view>
        <view class="flex-col shrink-0 self-start group_4 space-y-21">
          <view class="flex-col justify-start items-center self-center text-wrapper_4">
            <text class="font_2 text_3">推荐算法</text>
          </view>
          <view class="flex-col justify-start items-center text-wrapper_5"><text class="text_5">强化学习</text></view>
        </view>
      </view>
      <view class="flex-col justify-start items-center self-center text-wrapper_7">
        <text class="text_7">数据挖掘</text>
      </view>
    </view>
  </view>
</template>

<script>
  export default {
    components: {},
    props: {},
    data() {
      return {};
    },

    methods: {
		tojqxx() {
			uni.navigateTo({
				url:'/pages/jqxxjs/jqxxjs'
			})
		}
	},
  };
</script>

<style scoped lang="scss">
	@keyframes floating {
	  0% {
	    transform: translateY(0);
	  }
	  50% {
	    transform: translateY(-10px);
	  }
	  100% {
	    transform: translateY(0);
	  }
	}
	@keyframes floating1 {
	  0% {
	    transform: translateY(0);
	  }
	  50% {
	    transform: translateY(10px);
	  }
	  100% {
	    transform: translateY(0);
	  }
	}
  .page {
	  position: fixed;
    padding: 50rpx 46rpx 144rpx;
    background-image: linear-gradient(158.8deg, #cee5f2 44.5%, #eee7f2 100%);
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
	.font{
		color: #858d9c;
		margin: 0 auto;
		padding: 20rpx 30rpx;
		background-color: #c4cfe6;
		border-radius: 30rpx;
		font-weight: 700;
	}
    .group {
      padding-left: 38rpx;
      padding-right: 8rpx;
      .text-wrapper {
		  animation: floating1 2.5s infinite ease-in-out;
        padding: 96rpx 0 68rpx;
        background-image: radial-gradient(25% 25% at 75% 50%, #e8c3d92b 0%, #ebc5d6 100%);
        border-radius: 50%;
        width: 292rpx;
        height: 292rpx;
        .text {
          color: #b874a7;
          text-align: center;
          width: 188rpx;
        }
      }
      .text-wrapper_2 {
		  animation: floating 2s infinite ease-in-out;
        margin-top: 78rpx;
        padding: 84rpx 0 60rpx;
        border-radius: 50%;
        background-image: url('https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/64c797f95a7e3f03105ee874/6507d195ec886600112812ab/16952151953384546191.png');
        background-size: 100% 100%;
        background-repeat: no-repeat;
        width: 252rpx;
        height: 252rpx;
        .text_2 {
          color: #9e76e8;
          text-align: center;
          width: 156rpx;
        }
      }
    }
    .group_2 {
      padding-bottom: 12rpx;
      .space-y-33 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 66rpx;
        }
        .text-wrapper_3 {
			animation: floating 1.5s infinite ease-in-out;
          padding: 96rpx 0;
          background-image: radial-gradient(25% 25% at 75% 50%, #edceaf 0%, #edbbbb 100%);
          border-radius: 50%;
          .text_4 {
            color: #bd5f48;
            width: 160rpx;
          }
        }
        .text-wrapper_6 {
			animation: floating 2.5s infinite ease-in-out;
          margin-left: 20rpx;
          padding: 76rpx 0 64rpx;
          background-image: radial-gradient(25% 25% at 75% 50%, #f5f4dc2b 0%, #e8c580 100%);
          border-radius: 50%;
          .text_6 {
            color: #c79f50;
            text-align: center;
            width: 100rpx;
          }
        }
      }
      .group_4 {
        margin-right: 28rpx;
        margin-top: 14rpx;
        .text-wrapper_4 {
			animation: floating1 2s infinite ease-in-out;
          padding: 68rpx 0 48rpx;
          border-radius: 50%;
          background-image: url('https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/64c797f95a7e3f03105ee874/6507d195ec886600112812ab/16952151953413961413.png');
          background-size: 100% 100%;
          background-repeat: no-repeat;
          width: 220rpx;
          .text_3 {
            color: #5d8573;
            text-align: center;
            width: 118rpx;
          }
        }
        .text-wrapper_5 {
			animation: floating 2s infinite ease-in-out;
          padding: 128rpx 0 120rpx;
          background-image: radial-gradient(25% 25% at 75% 50%, #afedc92b 0%, #93cfed 100%);
          border-radius: 50%;
          width: 300rpx;
          .text_5 {
            color: #418a9e;
            font-size: 56rpx;
            font-family: SourceHanSansCN;
            font-weight: 700;
            line-height: 54rpx;
          }
        }
      }
      .space-y-21 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 42rpx;
        }
      }
    }
    .font_2 {
      font-size: 40rpx;
      font-family: SourceHanSansCN;
      line-height: 48rpx;
      font-weight: 700;
    }
    .font_1 {
      font-size: 48rpx;
      font-family: SourceHanSansCN;
      line-height: 58rpx;
      font-weight: 700;
    }
    .text-wrapper_7 {
		animation: floating 2s infinite ease-in-out;
      padding: 128rpx 0 132rpx;
      background-image: radial-gradient(25% 25% at 75% 50%, #e6d8e4 0%, #d4c6f5 100%);
      border-radius: 50%;
      width: 314rpx;
      .text_7 {
        color: #957fc9;
        font-size: 60rpx;
        font-family: SourceHanSansCN;
        font-weight: 700;
        line-height: 57rpx;
      }
    }
  }
  .space-y-35 {
    & > view:not(:first-child),
    & > text:not(:first-child),
    & > image:not(:first-child) {
      margin-top: 70rpx;
    }
  }
</style>