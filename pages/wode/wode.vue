<template>
	<view class="flex-col page">
		<view class="status_bar">
		    <!-- 这里是状态栏 -->
		</view>
	  <view class="flex-col flex-auto group">
	    <view class="flex-col relative section">
	      <view class="self-end section_2">
			  <image class="shezhi" src="../../static/shezhi.png" mode="heightFix"></image>
		  </view>
	      <view class="flex-col items-start group_2 space-y-10">
	        <text class="text">Hi，小灵</text>
	        <text class="text_2">灵犀号：2387063291</text>
	      </view>
	      <view class="section_3 pos">
			  <image src="../../static/lxzx.png" mode=""></image>
		  </view>
	    </view>
	    <view class="flex-col group_3">
	      <view class="flex-col items-center relative section_4 space-y-4">
	        <text class="font_1">咬住青山不放松，立根原在破岩中；</text>
	        <text class="font_1">千磨万击还坚劲，任尔东西南北风。</text>
	      </view>
	      <view class="flex-col group_4 space-y-17">
	        <view class="flex-row space-x-19">
	          <view class="flex-col equal-division-item space-y-8" @click="towodebaogao">
	            <text class="self-start font_2 text_3">我的报告</text>
	            <view class="flex-col items-start section_5 space-y-14">
	              <text class="font_3">最近更新</text>
	              <text class="font_4">2023.09.10</text>
	            </view>
	          </view>
	          <view class="flex-col equal-division-item space-y-8" @click="toxqrj">
	            <text class="self-start font_2 text_3">心情日记</text>
	            <view class="flex-col items-start section_5 space-y-14">
	              <text class="font_3">最近更新</text>
	              <text class="font_4">2023.09.10</text>
	            </view>
	          </view>
	        </view>
	        <view class="flex-col items-start section_6 space-y-38">
			  <view class="demo" @click="golljl">
				  <view class="mat">
				  	<image src="../../static/jilu.png" class="icon" mode="heightFix"></image>
					<text class="font_5">浏览记录</text>
				  </view>
				  <image src="../../static/jiantou.png" class="icon1" mode="heightFix"></image>
			  </view>
			  <view class="demo" @click="gorili">
				  <view class="mat">
				  	<image src="../../static/huodong.png" class="icon" mode="heightFix"></image>
					<text class="font_5">活动中心</text>
				  </view>
				<image src="../../static/jiantou.png" class="icon1" mode="heightFix"></image>
			  </view>
			  <view class="demo" @click="golsbg">
				  <view class="mat">
					<image src="../../static/baogao.png" class="icon" mode="heightFix"></image>
					<text class="font_5">历史报告</text>
				  </view>
				<image src="../../static/jiantou.png" class="icon1" mode="heightFix"></image>
			  </view>
			  <view class="demo">
				  <view class="mat">
					<image src="../../static/fuli.png" class="icon" mode="heightFix"></image>
					<text class="font_5">福利中心</text>
				  </view>
				<image src="../../static/jiantou.png" class="icon1" mode="heightFix"></image>
			  </view>
			  <view class="demo">
				  <view class="mat">
					<image src="../../static/zhanghao.png" class="icon" mode="heightFix"></image>
					<text class="font_5">账号管理</text>
				  </view>
				<image src="../../static/jiantou.png" class="icon1" mode="heightFix"></image>
			  </view>
			

	        </view>
	      </view>
	    </view>
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
			towodebaogao() {
				uni.navigateTo({
					url:'/pages/wodebaogao/wodebaogao'
				})
			},
			toxqrj() {
				uni.navigateTo({
					url:'/pages/xqrj/xqrj'
				})
			},
			golljl(){
				uni.navigateTo({
					url:'/pages/liulanjilu/liulanjilu'
				})
			},
			golsbg(){
				uni.navigateTo({
					url:'/pages/wodebaogao/wodebaogao'
				})
			},
			gorili(){
				uni.navigateTo({
					url:'/pages/rili/rili'
				})
			}
		}
	}
</script>

<style scoped lang="scss">
.page {
	position: fixed;
    background-color: #f5f5f5;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
	//background-image: linear-gradient(180deg, #ccf0f0 0%, #ebedff 51.2%, #ccf0f0 100%);
    .group {
      overflow-y: auto;
      .section {
        padding: 35rpx 40rpx 0;
        background-color: #d3e4f3;
        .section_2 {
          //margin-right: 68rpx;
          background-color: #00000000;
          width: 50rpx;
          height: 50rpx;
		  .shezhi{
			  height: 50rpx;
		  }
        }
        .group_2 {
          padding: 60rpx 0;
          .text {
            color: #202020;
            font-size: 50rpx;
            font-family: SegoeUI-Bold;
            font-weight: 700;
            line-height: 48rpx;
          }
          .text_2 {
            color: #202020;
            font-size: 24rpx;
            font-family: SegoeUI;
            line-height: 21rpx;
          }
        }
        .space-y-10 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 20rpx;
          }
        }
        .section_3 {
          background-color: #ffffff;
          border-radius: 50%;
          width: 140rpx;
          height: 140rpx;
		  overflow: hidden;
		  image{
			  width: 140rpx;
			  height: 140rpx;
		  }
        }
        .pos {
          position: absolute;
          right: 40rpx;
          top: 126rpx;
        }
      }
      .group_3 {
        padding: 40rpx 40rpx 0;
        .section_4 {
          padding: 36rpx 0 28rpx;
          background-color: #edf2f7;
          border-radius: 60rpx;
          box-shadow: 0px 6rpx 16rpx #8f8f8f29;
          .font_1 {
            font-size: 36rpx;
            font-family: SegoeUI;
            line-height: 44rpx;
            color: #202020;
          }
        }
        .space-y-4 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 8rpx;
          }
        }
        .group_4 {
          padding: 44rpx 0 54rpx;
          .space-x-19 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 38rpx;
            }
            .equal-division-item {
              flex: 1 1 316rpx;
              padding: 32rpx 16rpx 20rpx;
              background-color: #d0f2f0;
              border-radius: 24rpx;
              height: 246rpx;
              .font_2 {
                font-size: 40rpx;
                font-family: SegoeUI-Bold;
                line-height: 37rpx;
                font-weight: 700;
                color: #202020;
              }
              .text_3 {
                margin-left: 8rpx;
              }
              .section_5 {
                padding: 20rpx 16rpx 36rpx;
                background-color: #ffffff;
                border-radius: 24rpx;
                .font_3 {
                  font-size: 32rpx;
                  font-family: SegoeUI-Bold;
                  line-height: 30rpx;
                  font-weight: 700;
                  color: #aaaaaa;
                }
                .font_4 {
                  font-size: 32rpx;
                  font-family: SegoeUI-Bold;
                  line-height: 23rpx;
                  font-weight: 700;
                  color: #aaaaaa;
                }
              }
              .space-y-14 {
                & > view:not(:first-child),
                & > text:not(:first-child),
                & > image:not(:first-child) {
                  margin-top: 28rpx;
                }
              }
            }
          }
          .section_6 {
            padding: 48rpx 40rpx 48rpx;
            background-color: #ffffff;
            border-radius: 24rpx;
			.demo{
				width: 100%;
				display: flex;
				justify-content: space-between;
				
				.icon{
					height: 36rpx;
					margin-right: 15rpx;
				}
				.font_5 {
				  font-size: 36rpx;
				  font-family: SegoeUI;
				  line-height: 33rpx;
				  color: #202020;
				}
				.icon1{
					height: 36rpx;
					margin-right: 15rpx;
				}
			}
          }
          .space-y-38 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-top: 76rpx;
            }
          }
        }
        .space-y-17 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 34rpx;
          }
        }
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
</style>
