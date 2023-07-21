<template>
	<view class="flex-col page">
		<view class="ct_tab">
			<view class="ct_item" :class="{'ct_active' : 0 == tabCur}" @click="clickCtTab(0)">
				<text>文章</text>
			</view>
			<view class="ct_item" :class="{'ct_active' : 1 == tabCur}" @click="clickCtTab(1)">
				<text>视频</text>
			</view>

		</view>
		<view v-if="tabCur===0">
			<view class="tabCur1">
				<view class="flex-col relative group_3">
					
				  <view class="flex-row">
				    <view class="shrink-0 section_2">
						<image src="../../static/course02.png" mode="aspectFill"></image>
					</view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">健康观，随着医学的发展,人类对于健康的认识已经历了几个不...</text>
				      <text class="font_3">科普小达人</text>
					  <text class="font_4">7-21</text>
				    </view>
				  </view>
				  
				  <view class="flex-row">
				    <view class="shrink-0 section_2">
						<image src="../../static/lb1.jpg" mode="aspectFill"></image>
					</view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">健康观，随着医学的发展,人类对于健康的认识已经历了几个不同...</text>
				      <text class="font_3">科普小达人</text>
					  <text class="font_4">7-21</text>
				    </view>
				  </view>
				  
				  
				</view>
			</view>
		</view>
		<view v-if="tabCur===1">
			<view class="tabCur1">
				<view class="flex-col relative group_3">
					
				  <view class="flex-row">
				    <view class="shrink-0 section_2">
						<image src="../../static/course02.png" mode="aspectFill"></image>
					</view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">健康观，随着医学的发展,人类对于健康的认识已经历了几个不...</text>
				      <text class="font_3">科普小达人</text>
					  <text class="font_4">7-21</text>
				    </view>
				  </view>
				  
				  <view class="flex-row">
				    <view class="shrink-0 section_2"></view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">健康观，随着医学的发展,人类对于健康的认识已经历了几个不同...</text>
				      <text class="font_3">科普小达人</text>
					  <text class="font_4">7-21</text>
				    </view>
				  </view>
				  
				  <view class="flex-row">
				    <view class="shrink-0 section_2"></view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">健康观，随着医学的发展,人类对于健康的认识已经历了几个不同...</text>
				      <text class="font_3">科普小达人</text>
				  					  <text class="font_4">7-21</text>
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
				tabCur:0,
				list_lzTf4DFF: [null, null, null, null, null, null],
			};
		},
		methods:{
			clickCtTab(ctCur){
				this.tabCur  = ctCur
				console.log(this.tabCur )
			},
		}
	}
</script>

<style scoped lang="scss">
//顶部导航栏
.ct_tab{
	width: 100%;
	margin: 0 auto;
	padding: 15rpx 0;
	font-size: 45rpx;
	font-weight: bold;
	color: #c0c8d0;
	background: #edfeff;
	display: flex;
	justify-content: space-evenly;
	align-items: center;
}
.ct_item{
	//width: 20%;
	padding-bottom: 15rpx;
}
.ct_item text{//小横杠字体距离
	padding: 5rpx 0;
	
}
.ct_active{
	color: #000000;//字体颜色
}
.ct_active text{
	//小横杠
	border-bottom: 5px solid #65cbc8;
	
}
.tabCur1{
	//padding: 20rpx;
	//background: #007AFF;
	color: #aa55ff;
	//margin-top: 10rpx;
}
//-------------------------------------------------------------------
  .page {
    //padding: 0rpx 40rpx 24rpx;
    background-color: #ffffff;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;

    .group_3 {
	  padding: 0rpx 30rpx 24rpx;
      margin-top: 22rpx;
      padding-bottom: 200rpx;
      .section_2 {	  
		margin-bottom: 22rpx;
        background-color: #ebebeb;
        border-radius: 32rpx;
        width: 220rpx;
        height: 170rpx;
		overflow: hidden;
		image{
			width: 220rpx;
			height: 170rpx;
		}
      }
      .group_4 {
        margin: 8rpx 10rpx 0rpx 20rpx;
      }
      .space-y-4 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 8rpx;
        }
      }
      
      .font_2 {
        font-size: 26rpx;
        font-family: SegoeUI-Bold;
        line-height: 35rpx;
        font-weight: 700;
        color: #595959;
      }
      .font_3 {
        font-size: 26rpx;
        font-family: SegoeUI-Bold;
        line-height: 18rpx;
        font-weight: 700;
        color: #65cbc8;
      }
	  .font_4 {
	    font-size: 26rpx;

	    font-weight: 500;
	    color: #55557f;
	  }
    }
  }
</style>
