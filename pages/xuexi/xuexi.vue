<template>
	<view class="flex-col page space-y-22">
	  
	  <view class="flex-col space-y-10">
	    <view class="flex-row justify-between group_3">
	      <text class="self-start text_5">{{detail.name}}</text>
	      <view class="flex-col justify-start items-center self-center text-wrapper">
	        <text class="font_2 text_4">记笔记</text>
	      </view>
	    </view>
	    <text class="self-start font_2 text_6">就诊科室：{{detail.keshi}}</text>
	    <view class="flex-col">
	      <view class="flex-col items-start section_2 space-y-4">
	        <text class="font_4">概述：</text>
	        <text class="font_2">{{detail.gaishu}}</text>
	        
	      </view>
	      <view class="flex-col list space-y-16">
	        <view class="flex-col justify-start items-start list-item" >
	          <view class="group_4">
	            <text class="font_3">定义：</text>
	            <text class="font_2">{{detail.dingyi}}</text>
	          </view>
	        </view>
			
			<view class="flex-col justify-start items-start list-item" >
			  <view class="group_4">
			    <text class="font_3">就医：</text>
			    <text class="font_2">{{detail.jiuyi}}</text>
			  </view>
			</view>
			
			<view class="flex-col justify-start items-start list-item" >
			  <view class="group_4">
			    <text class="font_3">治疗：</text>
			    <text class="font_2">{{detail.zhiliao}}</text>
			  </view>
			</view>
			
			<view class="flex-col justify-start items-start list-item" >
			  <view class="group_4">
			    <text class="font_3">日常：</text>
			    <text class="font_2">{{detail.richang}}</text>
			  </view>
			</view>
			
	      </view>
	    </view>
	  </view>
	</view>
</template>

<script>
	let id;
	export default {
	  components: {},
	  data() {
	    return {
	      detail:{},
	      loadState:false
	    };
	  },
		onLoad(e){			
			id=e.id
		},
		onShow(){
			this.getDetail();
		},
		methods: {
			//获取详情-----------------------------------------------
			getDetail(){
				uniCloud.callFunction({
					name:"get_Study1_row",
					data:{
						id
					}
				}).then(res=>{						
					this.detail=res.result.data[0]
					this.loadState=true
					uni.setNavigationBarTitle({
						title:this.detail.title
					})
				})
			}
		}
	};
</script>

<style scoped lang="scss">
.page {
    padding: 40rpx 40rpx 134rpx;
    background-color: #ffffff;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    //position: fixed;
    .space-y-10 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 20rpx;
      }
      .group_3 {
        padding: 0 6rpx;
        .text_5 {
          //margin-top: 28rpx;
          color: #202020;
          font-size: 60rpx;
          font-family: SegoeUI-Bold;
          font-weight: 700;
          line-height: 84rpx;
        }
        .text-wrapper {
          padding: 24rpx 0;
          background-color: #65cbc8;
          border-radius: 40rpx;
          width: 178rpx;
          height: 74rpx;
          .text_4 {
            color: #ffffff;
            line-height: 29rpx;
          }
        }
      }
      .font_2 {
        font-size: 32rpx;
        font-family: SegoeUI-Bold;
        line-height: 38rpx;
        font-weight: 500;
        color: #78708c;
      }
	  .font_4 {
	    font-size: 32rpx;
	    font-family: SegoeUI-Bold;
	    line-height: 38rpx;
	    font-weight: 700;
	    color: #78708c;
	  }
      .text_6 {
        margin-left: 6rpx;
        color: #202020;
        line-height: 31rpx;
      }
      .section_2 {
		margin-top: 20rpx;
        padding: 28rpx 30rpx 28rpx 30rpx;
        background-color: #edf2f7;
        border-radius: 24rpx;
      }
      .space-y-4 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 8rpx;
        }
      }
      .list {
        padding-top: 36rpx;
        .list-item {
          padding: 28rpx 30rpx 28rpx;
          background-color: #edf2f7;
          border-radius: 24rpx;
          .group_4 {
            //margin-left: 28rpx;
            .font_3 {
              font-size: 48rpx;
              font-family: SegoeUI-Bold;
              line-height: 58rpx;
              font-weight: 700;
              color: #78708c;
            }
          }
        }
      }
      .space-y-16 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 32rpx;
        }
      }
    }
  }
  .space-y-22 {
    & > view:not(:first-child),
    & > text:not(:first-child),
    & > image:not(:first-child) {
      margin-top: 44rpx;
    }
  }
</style>
