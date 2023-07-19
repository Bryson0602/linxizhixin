<template>
	<view class="flex-col page space-y-3">
		<view class="status_bar">
		    <!-- 这里是状态栏 -->
		</view>
	  <view class="flex-col group">
	    <view class="flex-row justify-center items-center group_2 space-x-10">
		  <image class="dinwei" src="../../static/dinwei.png" mode="heightFix"></image>
	      <text class="text">浙江</text>
	      <view class="flex-row items-center section">
	        <image
	          class="shrink-0 image"
	          src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385873872537315.png"
	        />
	        <text class="font_1 text_2">如何正确面对生活中的焦虑</text>
	        <view class="flex-col justify-start items-center shrink-0 text-wrapper">
	          <text class="font_1 text_3">搜索</text>
	        </view>
	      </view>
		  <image class="dinwei" src="../../static/rili.png" mode="heightFix"></image>
	    </view>
	    <swiper class="flex-row justify-center section_2 space-x-4" circular indicator-dots autoplay interval="3000" duration="500" indicator-active-color="#fff" indicator-inactive-color="#aaa"  style="border-radius: 10px;">
	        <swiper-item v-for="item in bannerList" :key="item.id">
	          <image style="width: 100%; vertical-align: bottom;" mode="aspectFill" :src="item.picUrl"></image>
	        </swiper-item>
	    </swiper>
	    <view class="flex-row group_3 space-x-13">
	      <view class="flex-col flex-auto self-center relative section_4">
	        <text class="self-start font_2 text_4">HI! 今天是{{weekday}}</text>
	        <view class="flex-col justify-start items-center relative text-wrapper_2">
	          <text class="font_2 text_5">记录每日心情</text>
	        </view>
	        <view class="flex-row group_4 space-x-4">
	          <view class="flex-col justify-start items-center text-wrapper_3" :class="dayindex===1?'text-wrapper_4':''"><text class="font_4" :class="dayindex===1?'text_6':''">1</text></view>
	          <view class="flex-col justify-start items-center text-wrapper_3" :class="dayindex===2?'text-wrapper_4':''"><text class="font_4" :class="dayindex===2?'text_6':''">2</text></view>
	          <view class="flex-col justify-start items-center text-wrapper_3" :class="dayindex===3?'text-wrapper_4':''"><text class="font_4" :class="dayindex===3?'text_6':''">3</text></view>
	          <view class="flex-col justify-start items-center text-wrapper_3" :class="dayindex===4?'text-wrapper_4':''"><text class="font_4" :class="dayindex===4?'text_6':''">4</text></view>
	          <view class="flex-col justify-start items-center text-wrapper_3" :class="dayindex===5?'text-wrapper_4':''"><text class="font_4" :class="dayindex===5?'text_6':''">5</text></view>
	          <view class="flex-col justify-start items-center text-wrapper_3" :class="dayindex===6?'text-wrapper_4':''"><text class="font_4" :class="dayindex===6?'text_6':''">6</text></view>
	          <view class="flex-col justify-start items-center text-wrapper_3" :class="dayindex===0?'text-wrapper_4':''"><text class="font_4" :class="dayindex===0?'text_6':''">7</text></view>
	        </view>
	      </view>
	      <view class="flex-col justify-start items-center shrink-0 self-start section_3">
	        <view class="flex-col items-center section_5 space-y-6">
	          <text class="font_3">开始</text>
	          <text class="font_3">测试</text>
	        </view>
	      </view>
	    </view>
	    <view class="flex-col justify-start relative section_6">
	      <view class="grid">
	        <view class="flex-col items-center relative grid-item">
	          <image
	            class="image_3"
	            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385864418377735.png"
	          />
	          <text class="font_1">扫一扫</text>
	        </view>
	        <view class="flex-col items-center relative grid-item">
	          <image
	            class="image_3"
	            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385864426317722.png"
	          />
	          <text class="font_1">签到</text>
	        </view>
	        <view class="flex-col items-center relative grid-item">
	          <image
	            class="image_3"
	            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385864433788524.png"
	          />
	          <text class="font_1">话题</text>
	        </view>
	        <view class="flex-col items-center relative grid-item">
	          <image
	            class="image_3"
	            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385864440525868.png"
	          />
	          <text class="font_1">反馈</text>
	        </view>
	        <view class="flex-col items-center relative grid-item">
	          <image
	            class="image_3"
	            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385867267432071.png"
	          />
	          <text class="font_1">收藏</text>
	        </view>
	        <view class="flex-col items-center relative grid-item">
	          <image
	            class="image_3"
	            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385867369836328.png"
	          />
	          <text class="font_1">社团</text>
	        </view>
	        <view class="flex-col items-center relative grid-item">
	          <image
	            class="image_3"
	            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385867430965549.png"
	          />
	          <text class="font_1">圈子</text>
	        </view>
	        <view class="flex-col items-center relative grid-item">
	          <image
	            class="image_3"
	            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385868814769343.png"
	          />
	          <text class="font_1">学习</text>
	        </view>
	      </view>
	    </view>
	    <view class="flex-row justify-between group_5">
	      <view class="flex-col justify-start self-start relative group_7">
	        <view class="section_7"></view>
	        <text class="text_7 pos">大家在看</text>
	      </view>
	      <view class="flex-row self-center group_6 space-x-10">
	        <view class="flex-col justify-start items-center relative text-wrapper_5">
	          <text class="font_5 text_8">推荐</text>
	        </view>
	        <view class="flex-col justify-start items-center relative text-wrapper_6">
	          <text class="font_5">收藏</text>
	        </view>
	        <view class="flex-col justify-start items-center text-wrapper_6"><text class="font_5">关注</text></view>
	      </view>
	    </view>
	  </view>
	  <view class="flex-col justify-start relative">
	    <view class="group_8"></view>
	    <view class="grid_2 pos_2">
			
	      <view class="flex-col relative grid-item_2">
	        <view class="section_8"></view>
	        <view class="flex-col items-start group_9 space-y-4">
	          <text class="font_6 text_9">大家好~这是我来到灵犀</text>
	          <text class="font_6 text_10">知心的第一条帖子，希望</text>
	          <text class="font_6 text_11">能和大家多交流下心得。</text>
	          <view class="section_11 view"></view>
	        </view>
	      </view>
	      <view class="flex-col relative grid-item_3 space-y-28">
	        <view class="section_9"></view>
	        <view class="self-start section_11 view_2"></view>
	      </view>
		  
		  <view class="flex-col relative grid-item_2">
		    <view class="section_8"></view>
		    <view class="flex-col items-start group_9 space-y-4">
		      <view class="section_11 view"></view>
		    </view>
		  </view>
		  <view class="flex-col relative grid-item_3 space-y-28">
		    <view class="section_9"></view>
		    <view class="self-start section_11 view_2"></view>
		  </view>
		  
		  
		  <view class="flex-col relative grid-item_2">
		    <view class="section_8"></view>
		    <view class="flex-col items-start group_9 space-y-4">
		      <view class="section_11 view"></view>
		    </view>
		  </view>
		  <view class="flex-col relative grid-item_3 space-y-28">
		    <view class="section_9"></view>
		    <view class="self-start section_11 view_2"></view>
		  </view>
		  
	      <!-- <view class="flex-col relative grid-item_3">
	        <view class="section_12"></view>
	        <text class="self-start font_1 text_17">今天心情真好呀~</text>
	        <view class="flex-row group_13 space-x-4">
	          <view class="section_11"></view>
	          <text class="self-start font_8 text_19">游山</text>
	        </view>
	      </view>
	      <view class="flex-col grid-item_4 space-y-6">
	        <view class="section_8"></view>
	        <view class="flex-col items-center space-y-4">
	          
	      
	        </view>
	        <view class="flex-col group_12">

	          <view class="flex-row group_14 space-x-4">
	            <view class="section_11"></view>
	            <text class="self-start font_8 text_20"></text>
	          </view>
	        </view>
	      </view>
	      <view class="flex-col justify-start relative grid-item_5"><view class="section_15"></view></view>
	      <view class="flex-col justify-start grid-item_5"><view class="section_15"></view></view> -->
	    </view>
	    
	  </view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				dayindex:0,
				bannerList: [//轮播图
				  {id: 1, picUrl: '/static/lb1.jpg'},
				  {id: 2, picUrl: '/static/lb2.jpeg'},
				  {id: 3, picUrl: '/static/lb3.jpg'},
				  {id: 4, picUrl: '/static/lb4.jpg'},
				  {id: 5, picUrl: '/static/lb5.jpg'},
				]
			};
		},
		methods: {
		  
		},
		computed: {
		  weekday() {
		    const weekdays = ['周日', '周一', '周二', '周三', '周四', '周五', '周六']
		    const date = new Date()
			this.dayindex=date.getDay()
		    return weekdays[date.getDay()]
		  }
		}
	}
</script>

<style scoped lang="scss">
.page {
	position: fixed;
    padding-top: 15rpx;
    background-image: linear-gradient(180deg, #ccf0f0 0%, #eff0ff 21.4%, #ffffff 48.5%, #eff0ff 76.7%, #ccf0f0 100%);
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .group {
      padding: 0 40rpx;
      .group_2 {
        padding: 0 44rpx 22rpx;
		.dinwei{
			height: 45rpx;
		}
        .text {
          color: #000000;
          font-size: 28rpx;
          font-family: SegoeUI-Bold;
          font-weight: 700;
          line-height: 26rpx;
        }
        .section {
          padding: 4rpx 6rpx 4rpx 16rpx;
          background-color: #ffffff;
          border-radius: 24rpx;
          box-shadow: 0px 10rpx 8rpx #9695a129;
          height: 65rpx;
          .text_2 {
            margin-left: 12rpx;
            color: #d5d5d5;
          }
          .text-wrapper {
            margin-left: 24rpx;
            padding: 8rpx 0;
            background-color: #97dbcb;
            border-radius: 24rpx;
            width: 92rpx;
            height: 40rpx;
            .text_3 {
              color: #f2f3f5;
            }
          }
        }
      }
      .space-x-10 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 20rpx;
        }
      }
      .section_2 {
        
        overflow: hidden;
		background: #fff;
		box-shadow: 0px 5px 5px rgba(0, 0, 0, 0.1);
      }
      .group_3 {
        padding: 30rpx 0;
        .section_4 {
          padding: 16rpx 14rpx 0;
          background-image: linear-gradient(180deg, #b8eeec 0%, #f2eeff 79.7%, #ffffff 100%);
          border-radius: 32rpx;
          box-shadow: 0px 6rpx 12rpx #dbdbdb;
          height: 264rpx;
          .font_2 {
            font-size: 36rpx;
            font-family: SegoeUI-Bold;
            line-height: 44rpx;
            font-weight: 700;
          }
          .text_4 {
            margin-left: 8rpx;
            color: #71768f;
          }
          .text-wrapper_2 {
            margin: 40rpx 8rpx 0;
            padding: 24rpx 0;
            background-color: #ffffff;
            border-radius: 60rpx;
            box-shadow: 0px 6rpx 12rpx #00000029;
            .text_5 {
              color: #202020;
              line-height: 33rpx;
            }
          }
          .group_4 {
            padding: 30rpx 0 16rpx;
            .text-wrapper_3 {
              flex: 1 1 44rpx;
              padding: 8rpx 0;
              background-color: #ece7f3;
              border-radius: 50%;
              height: 44rpx;
            }
            .text-wrapper_4 {
              padding: 8rpx 0;
              flex: 1 1 44rpx;
              background-color: #ffffff;
              border-radius: 50%;
              height: 44rpx;
              .text_6 {
                color: #78708c;
              }
            }
            .font_4 {
              font-size: 36rpx;
              font-family: SegoeUI-Bold;
              line-height: 26rpx;
              font-weight: 700;
              color: #b2b6cf;
            }
          }
        }
        .section_3 {
          margin-right: 4rpx;
          padding: 24rpx 0;
          background-color: #7bdddb;
          box-shadow: 0px 6rpx 16rpx #dbdbdb;
          border-radius: 50%;
          width: 258rpx;
          height: 258rpx;
          .section_5 {
            padding: 48rpx 0 32rpx;
            background-color: #e9faff;
            box-shadow: 0px 6rpx 16rpx #46aca9;
            border-radius: 50%;
            width: 206rpx;
          }
        }
      }
      .space-x-13 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 26rpx;
        }
      }
      .section_6 {
        background-color: #ffffffb3;
        border-radius: 60rpx;
        box-shadow: 0px 6rpx 24rpx #dbdbdb;
        height: 243rpx;
        .grid {
          padding: 0 16rpx;
          height: 243rpx;
          display: grid;
          grid-template-columns: repeat(4, 1fr);
          .grid-item {
            padding: 12rpx 0 16rpx;
            .image_3 {
              width: 64rpx;
              height: 64rpx;
            }
          }
        }
      }
      .group_5 {
        padding-top: 24rpx;
        .group_7 {
          margin-top: 32rpx;
          padding-top: 28rpx;
          width: 196rpx;
          .section_7 {
            background-color: #bec3eb;
            height: 24rpx;
          }
          .text_7 {
            color: #202020;
            font-size: 44rpx;
            font-family: SegoeUI-Bold;
            font-weight: 700;
            line-height: 41rpx;
            width: 178rpx;
          }
          .pos {
            position: absolute;
            left: 50%;
            top: 0;
            transform: translateX(-50%);
          }
        }
        .group_6 {
          margin-right: 22rpx;
          .text-wrapper_5 {
            padding: 32rpx 0;
            background-color: #eae0f0;
            box-shadow: 0px 6rpx 12rpx #00000029;
            border-radius: 50%;
            width: 90rpx;
            height: 90rpx;
            .text_8 {
              line-height: 29rpx;
            }
          }
          .text-wrapper_6 {
            padding: 32rpx 0;
            background-color: #ffffff;
            box-shadow: 0px 6rpx 12rpx #00000029;
            border-radius: 50%;
            width: 90rpx;
            height: 90rpx;
          }
          .font_5 {
            font-size: 32rpx;
            font-family: SegoeUI-Bold;
            line-height: 30rpx;
            font-weight: 700;
            color: #78708c;
          }
        }
      }
    }
    .group_8 {
      margin: 0 28rpx;
      opacity: 0.49;
      border-radius: 24rpx 24rpx 0 0;
      height: 1320rpx;
    }
    .grid_2 {
      height: 1296rpx;
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      row-gap: 26rpx;
      column-gap: 22rpx;
      .grid-item_2 {
        background-color: #f3f4ff;
        border-radius: 40rpx;
        box-shadow: 0px 6rpx 12rpx #00000029;
        .group_9 {
          padding: 8rpx 24rpx;
          .text_9 {
            line-height: 28rpx;
          }
          .text_10 {
            line-height: 28rpx;
          }
          .text_11 {
            line-height: 28rpx;
          }
          .view {
            margin-left: 8rpx;
          }
        }
      }
      .grid-item_3 {
        padding-bottom: 10rpx;
        background-color: #f3f4ff;
        border-radius: 40rpx;
        box-shadow: 0px 6rpx 12rpx #00000029;
        .section_9 {
          background-color: #ffffff;
          border-radius: 40rpx 40rpx 0px 0px;
          height: 318rpx;
        }
        .view_2 {
          margin-left: 28rpx;
        }
        .section_12 {
          background-color: #ffffff;
          border-radius: 40rpx 40rpx 0px 0px;
          height: 326rpx;
        }
        .text_17 {
          margin-left: 20rpx;
          margin-top: 20rpx;
          color: #1e1c1c;
        }
        .group_13 {
          margin-top: 4rpx;
          padding: 0 34rpx;
          .text_19 {
            margin-top: 24rpx;
          }
        }
      }
      .space-y-28 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 56rpx;
        }
      }
      .section_11 {
        background-color: #595959;
        border-radius: 50%;
        width: 48rpx;
        height: 46rpx;
      }
      // .grid-item_4 {
      //   padding-bottom: 12rpx;
      //   filter: drop-shadow(0px 6rpx 6rpx #00000029);
      //   background-image: url('https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385864416810221.png');
      //   background-size: 100% 100%;
      //   background-repeat: no-repeat;
      //   .group_12 {
      //     padding: 0 20rpx;
      //     .text_18 {
      //       line-height: 28rpx;
      //     }
      //     .group_14 {
      //       padding: 0 8rpx;
      //       .text_20 {
      //         margin-top: 24rpx;
      //       }
      //     }
      //   }
      // }
      .section_8 {
        background-color: #ffffff;
        border-radius: 40rpx 40rpx 0px 0px;
        height: 260rpx;
      }
      .font_6 {
        font-size: 24rpx;
        font-family: SegoeUI-Bold;
        line-height: 26rpx;
        font-weight: 700;
        color: #1e1c1c;
      }
      .font_8 {
        font-size: 16rpx;
        font-family: SegoeUI-Bold;
        line-height: 15rpx;
        font-weight: 700;
        color: #1e1c1c;
      }
      // .grid-item_5 {
      //   padding-bottom: 12rpx;
      //   background-color: #e7e7e7;
      //   border-radius: 40rpx 40rpx 0 0;
      //   box-shadow: 0px 6rpx 12rpx #00000029;
      //   .section_15 {
      //     background-color: #ffffff;
      //     border-radius: 40rpx;
      //     height: 372rpx;
      //   }
      // }
    }
    .pos_2 {
      position: absolute;
      left: 50rpx;
      right: 50rpx;
      top: 24rpx;
    }
    .font_1 {
      font-size: 24rpx;
      font-family: SegoeUI-Bold;
      line-height: 22rpx;
      font-weight: 700;
      color: #78708c;
    }
    .space-x-4 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-left: 8rpx;
      }
    }
    .space-y-6 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 12rpx;
      }
    }
    .section_10 {
      padding: 12rpx 52rpx 16rpx;
      background-image: url('https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385874156323161.png');
      background-size: 100% 100%;
      background-repeat: no-repeat;
      .space-x-39 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 78rpx;
        }
        .group_10 {
          width: 55rpx;
          .section_13 {
            background-color: #65cbc8;
            border-radius: 50%;
            width: 30rpx;
            height: 30rpx;
          }
        }
        .space-y-8 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 16rpx;
          }
          .text-wrapper_7 {
            padding: 40rpx 0 36rpx;
            background-color: #65cbc8;
            box-shadow: 0px 6rpx 12rpx #dbdbdb;
            border-radius: 50%;
            width: 112rpx;
            .text_12 {
              color: #ffffff;
              line-height: 34rpx;
            }
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
      .group_11 {
        margin-right: 12rpx;
        .section_14 {
          background-color: #7bdddb;
          border-radius: 50%;
          width: 26rpx;
          height: 26rpx;
        }
        .text_14 {
          line-height: 19rpx;
        }
      }
      .space-y-18 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 36rpx;
        }
      }
    }
    .pos_3 {
      position: absolute;
      left: 0;
      right: 0;
      top: 400rpx;
    }
    .space-y-4 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 8rpx;
      }
      .text_15 {
        line-height: 28rpx;
      }
      .text_16 {
        line-height: 28rpx;
      }
      .image_4 {
        width: 16rpx;
        height: 18rpx;
      }
      .text_13 {
        line-height: 19rpx;
      }
    }
    .font_7 {
      font-size: 20rpx;
      font-family: SegoeUI-Bold;
      line-height: 18rpx;
      font-weight: 700;
      color: #78708c;
    }
    .font_3 {
      font-size: 48rpx;
      font-family: SegoeUI-Bold;
      line-height: 58rpx;
      font-weight: 700;
      color: #424263;
    }
    .image {
      width: 32rpx;
      height: 28rpx;
    }
  }
  .space-y-3 {
    & > view:not(:first-child),
    & > text:not(:first-child),
    & > image:not(:first-child) {
      margin-top: 6rpx;
    }
  }
</style>
