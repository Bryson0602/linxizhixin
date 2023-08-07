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
					
				  <view class="flex-row"@click="gojilu">
				    <view class="shrink-0 section_2">
						<image src="../../static/lsjl.jpg" mode="aspectFill"></image>
					</view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">转载｜《头脑特工队》电影赏析：在这部奥斯卡金像奖最佳...</text>
				      <text class="font_3">幸福联盟+</text>
					  <text class="font_4">9-10</text>
				    </view>
				  </view>
				  
				  <view class="flex-row"@click="gojilu1">
				    <view class="shrink-0 section_2">
						<image src="../../static/lsjl1.png" mode="aspectFill"></image>
					</view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">因为颜值，我对他一见钟情了？天性是百发百中，万无一失的...</text>
				      <text class="font_3">幸福联盟+</text>
					  <text class="font_4">9-10</text>
				    </view>
				  </view>
				  
				  <view class="flex-row"@click="gojilu2">
				    <view class="shrink-0 section_2">
						<image src="../../static/lsjl2.png" mode="aspectFill"></image>
					</view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">继星座之后，MBTI也给你贴标签了吗？MBTI真的很神奇啊...</text>
				      <text class="font_3">幸福联盟+</text>
				  	  <text class="font_4">9-9</text>
				    </view>
				  </view>
				  
				  <view class="flex-row"@click="gojilu3">
				    <view class="shrink-0 section_2">
						<image src="../../static/lsjl3.png" mode="aspectFill"></image>
					</view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">毕业季 | 来时星辰大海，未来不止诗和月光：大学四年的沙漏...</text>
				      <text class="font_3">幸福联盟+</text>
				  	  <text class="font_4">9-9</text>
				    </view>
				  </view>
				  
				  <view class="flex-row"@click="gojilu4">
				    <view class="shrink-0 section_2">
						<image src="../../static/lsjl4.jpg" mode="aspectFill"></image>
					</view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">不确定的生活，也要勇敢去爱：#1信息过滤——摒弃噪音...</text>
				      <text class="font_3">幸福联盟+</text>
				  	  <text class="font_4">9-8</text>
				    </view>
				  </view>
				  
				  <view class="flex-row"@click="gojilu5">
				    <view class="shrink-0 section_2">
						<image src="../../static/lsjl5.png" mode="aspectFill"></image>
					</view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">和博物馆来一场心灵的约会，聊聊过去、当下和未来...</text>
				      <text class="font_3">幸福联盟+</text>
				  	  <text class="font_4">9-7</text>
				    </view>
				  </view>
				  
				  <view class="flex-row"@click="gojilu6">
				    <view class="shrink-0 section_2">
						<image src="../../static/lsjl6.jpg" mode="aspectFill"></image>
					</view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">降低考前精神内耗，你需要区分这两种疲惫：想象一下我们尽...</text>
				      <text class="font_3">幸福联盟+</text>
				  	  <text class="font_4">9-7</text>
				    </view>
				  </view>
				  
				  <view class="flex-row"@click="gojilu7">
				    <view class="shrink-0 section_2">
						<image src="../../static/lsjl7.jpg" mode="aspectFill"></image>
					</view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">别做互联网的“松鼠”，要做收藏界的“实干家”：在碎片化信息...</text>
				      <text class="font_3">幸福联盟+</text>
				  	  <text class="font_4">9-7</text>
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
					  <text class="font_4">9-10</text>
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
			gojilu(){
				uni.navigateTo({
					url:'/pages/wzdetail/wzdetail?id=64bb7cb3337a9f4db7919615'
				})
			},
			gojilu1(){
				uni.navigateTo({
					url:'/pages/wzdetail/wzdetail?id=64ba49d7e0ec19bea192a2f4'
				})
			},
			gojilu2(){
				uni.navigateTo({
					url:'/pages/wzdetail/wzdetail?id=64bbcf9021821b2af5cc57ec'
				})
			},
			gojilu3(){
				uni.navigateTo({
					url:'/pages/wzdetail/wzdetail?id=64bb8fcea7c432baa0677fc5'
				})
			},
			gojilu4(){
				uni.navigateTo({
					url:'/pages/wzdetail/wzdetail?id=64bbda86652341bd64d48e59'
				})
			},
			gojilu5(){
				uni.navigateTo({
					url:'/pages/wzdetail/wzdetail?id=64bdf32f7ad52ddc64db6f4e'
				})
			},
			gojilu6(){
				uni.navigateTo({
					url:'/pages/wzdetail/wzdetail?id=64bbc0df2139291cebbb4c35'
				})
			},
			gojilu7(){
				uni.navigateTo({
					url:'/pages/wzdetail/wzdetail?id=64bb8094bd0220bf8c7b367b'
				})
			}
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
		margin-bottom: 30rpx;
        background-color: #ebebeb;
        border-radius: 32rpx;
        width: 220rpx;
        height: 160rpx;
		overflow: hidden;
		image{
			width: 220rpx;
			height: 160rpx;
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
        font-size: 28rpx;
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
