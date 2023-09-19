<template>
	<view class="flex-col page space-y-262">
	
	  <image mode="aspectFit" class="img" src="https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/90452b56-9816-44e6-a356-9a6ad2b352de.jpg"></image>
	  <view class="flex-col space-y-9">
	    <image
	      class="self-end image"
	      src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/64c797f95a7e3f03105ee874/6507d195ec886600112812ab/16950206876524986171.png"
	    />
	    <view class="flex-col justify-start relative group">
	      <view class="flex-col section_2 space-y-14">
	        <view class="flex-row justify-between items-center group_3">
	          <view class="flex-col relative group_4">
	            <view class="shrink-0 self-start section_3"></view>
	            <text class="self-end font_2 text_5">筛选</text>
	            <text class="text_3 pos_2">为你推荐</text>
	          </view>
	          <view class="flex-col justify-start items-center text-wrapper">
	            <text class="font_2 text_4">学习记录</text>
	          </view>
	        </view>
			
	        <view class="flex-col section_4 space-y-12">
	          <view class="flex-col items-start section_5 space-y-4">
				  <image class="im"  mode="aspectFill" src="https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/213cada9-229c-4b09-90fe-d1f99c32feca.png"></image>
	            <text class="font_1 text_6">AI技术大解析：灵犀知心背后的秘密！</text>
	          </view>
			  <view class="flex-col items-start section_5 space-y-4">
			      <image class="im"  mode="aspectFill" src="https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/cce3520b-3d63-4f75-847b-b43bd9e44774.jpeg"></image>
			    <text class="font_1 text_6">跨越时空的智能对话：AI的无限可能</text>
			  </view>
			  <view class="flex-col items-start section_5 space-y-4">
				  <image class="im"  mode="aspectFill" src="https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/3043f476-0181-4e49-8d0c-a44844aa7af3.jpeg"></image>
			    <text class="font_1 text_6">人工智能引领潮流：探索智能科技的新纪元</text>
			  </view>
	          
	        </view>
	        
	      </view>
	      <view class="flex-col section space-y-16 pos">
	        <view class="flex-col  group_2 space-y-4">
	          <text class="font_1">人工智能：未来的引领者</text>
	        </view>
	        <text class="font_5">在科技的海洋中，人工智能（AI）如同一颗璀璨的明珠，以其独特的魅力吸引着全球的目光。</text>
	        <view class="flex-row items-center space-x-8">
	          <text class="font_3 text_2">浏览量：20.6万</text>
	          
	          <text class="font_3">2023年9月8日</text>
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
				
			}
		},
		methods: {
			
		}
	}
</script>

<style scoped lang="scss">
	.im{
		border-radius: 15rpx 15rpx 0rpx 0rpx;
		width:665rpx;
		height:300rpx;
		
	}
	.font_5{
		font-size: 30rpx;
		font-family: SegoeUI-Bold;
		color:#7d7d7d;
		background-color: white;
		font-weight: 700;
		width:610rpx;
		margin-left: -1%;
		border-radius: 16rpx;
		padding-left: 3%;
		padding-right: 1%;
		padding-bottom: 5px;
	}
	.img{
		width:750rpx;
		margin-top:-5%;
	}
.page {
  
  background-image: linear-gradient(180deg, #ccf0f0 0%, #ebedff 52.9%, #ebedff 100%);
  width: 100%;
  
  
  height: 100%;
  .text {
    color: #202020;
    font-size: 48rpx;
    font-family: SegoeUI-Bold;
    font-weight: 700;
    line-height: 45rpx;
  }
  .space-y-9 {
    & > view:not(:first-child),
    & > text:not(:first-child),
    & > image:not(:first-child) {
      margin-top: 18rpx;
    }
    .image {
		margin-top:-14.5%;
      margin-right: 64rpx;
      width: 64rpx;
      height: 64rpx;
    }
    .group {
	
      padding-top: 128rpx;
      .section_2 {
        padding: 174rpx 40rpx 0;
        background-color: #edf1f6;
        .group_3 {
          padding: 0 16rpx;
          .group_4 {
            padding-top: 4rpx;
            width: 238rpx;
            height: 35rpx;
            .section_3 {
              margin-top: 34rpx;
              background-color: #65cbc8;
              width: 148rpx;
              height: 12rpx;
            }
            .text_5 {
              margin-top: -28rpx;
              color: #b4b4b4;
            }
            .text_3 {
              color: #202020;
              font-size: 32rpx;
              font-family: SegoeUI-Bold;
              font-weight: 700;
              line-height: 29rpx;
            }
            .pos_2 {
              position: absolute;
			  
              left: 12rpx;
              top: 90%;
              transform: translateY(-50%);
            }
          }
          .text-wrapper {
			  margin-top:7%;
            margin-right: 10rpx;
            padding: 8rpx 0;
            background-color: #65cbc8;
            border-radius: 60rpx;
            width: 156rpx;
            height: 46rpx;
            .text_4 {
              color: #ffffff;
            }
          }
        }
        .section_4 {
          margin-right: 8rpx;
          padding-bottom: 20rpx;
          background-color: #edf1f6;
          border-radius: 8rpx;
          
          .section_5 {
            
            background-color: #ffffff;
            border-radius: 8rpx;
            padding-bottom: 15rpx;
            .text_6 {
			padding-top: 5rpx;
              font-size: 33rpx;
			  width:665rpx;
              margin-left: 15rpx;
            }
          }
          .text_7 {
           font-size: 33rpx;
           margin-left: 15rpx;
          }
        }
        .space-y-12 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 44rpx;
          }
        }
        .section_6 {
          margin-right: 8rpx;
          background-color: #ffffff;
          border-radius: 8rpx 8rpx 0 0;
          box-shadow: 0px 6rpx 12rpx #c3c5ca29;
          height: 134rpx;
        }
      }
      .space-y-14 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 28rpx;
        }
      }
      .section {
        padding: 28rpx 40rpx;
        background-color: #ffffff;
        box-shadow: 0px 6rpx 12rpx #bdbdbd29;
        .group_2 {
          padding: 0 8rpx;
        }
        .space-x-8 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-left: 16rpx;
          }
          .font_3 {
            font-size: 20rpx;
            font-family: SegoeUI-Bold;
            line-height: 19rpx;
            font-weight: 700;
            color: #a9a9a9;
          }
          .text_2 {
            line-height: 18rpx;
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
      .pos {
        position: absolute;
        left: 0;
        right: 0;
        top: 0;
      }
      .space-y-4 {
		
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          
        }
      }
      .font_1 {
        font-size: 40rpx;
        font-family: SegoeUI-Bold;
        line-height: 48rpx;
        font-weight: 700;
        color: #787a8c;
      }
      .font_2 {
        font-size: 28rpx;
        font-family: SegoeUI-Bold;
        line-height: 26rpx;
        font-weight: 700;
        color: #787a8c;
      }
    }
  }
}
.space-y-262 {
  & > view:not(:first-child),
  & > text:not(:first-child),
  & > image:not(:first-child) {
    
  }
}
</style>
