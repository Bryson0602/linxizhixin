<template>
	<view class="flex-col page">
		<view class="ct_tab">
			<view class="ct_item" :class="{'ct_active' : 0 == tabCur}" @click="clickCtTab(0)">
				<text>AI学习知识</text>
			</view>
			<view class="ct_item" :class="{'ct_active' : 1 == tabCur}" @click="clickCtTab(1)">
				<text>错题集</text>
			</view>

		</view>
		<view v-if="tabCur===0">
			<view class="tabCur1">
				<view class="flex-col relative group_3">
					
					<view class="flex-row" @click="gojilu3">
					  <view class="shrink-0 section_2">
											<image src="../../static/jqxx.png" mode="aspectFill"></image>
										</view>
					  <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
					    <text class="font_2">机器学习：学无止境</text>
					    <text class="font_3">机器学习</text>
						  <text class="font_4">9-8</text>
						   <view class="line"></view>
					  </view>
					</view>
					
					<view class="flex-row" @click="gojilu8">
					  <view class="shrink-0 section_2">
											<image src="../../static/nlp.png" mode="aspectFill"></image>
										</view>
					  <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
					    <text class="font_2">NLP的力量：如何让机器理解人类语言</text>
					    <text class="font_3">NLP技术</text>
						  <text class="font_4">9-8</text>
						   <view class="line"></view>
					  </view>
					</view>
					
				  <view class="flex-row" @click="gojilu">
				    <view class="shrink-0 section_2">
						<image src="https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/45da393a-bb61-48b3-9579-3c8e467341ef.jpg" mode="aspectFill"></image>
					</view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">AI的发展史：一部人类智慧的革命史诗</text>
				      <text class="font_3">历史科普</text>
					  <text class="font_4">9-8</text>
					   <view class="line"></view>
				    </view>
				  </view>
				  
				  <view class="flex-row" >
				    <view class="shrink-0 section_2">
						<image src="../../static/mssb.png" mode="aspectFill"></image>
					</view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">走进模式识别技术</text>
				      <text class="font_3">模式识别</text>
					  <text class="font_4">9-8</text>
					   <view class="line"></view>
				    </view>
				  </view>
				  
				  <view class="flex-row" >
				    <view class="shrink-0 section_2">
						<image src="https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/964f1ee4-e616-4228-b968-ab97e6117483.jpeg" mode="aspectFill"></image>
					</view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">人工智能的历史旅程：从无到有的创新之路</text>
				      <text class="font_3">历史科普</text>
				  	  <text class="font_4">9-7</text>
					   <view class="line"></view>
				    </view>
				  </view>
				  
				  <uni-divider type="solid"></uni-divider>
				  <view class="flex-row" >
				    <view class="shrink-0 section_2">
						<image src="../../static/AImx.png" mode="aspectFill"></image>
					</view>
				    <view class="flex-col items-start flex-auto self-start group_4 space-y-4">
				      <text class="font_2">引领潮流的AI大模型</text>
				      <text class="font_3">AI大模型</text>
				  	  <text class="font_4">9-6</text>
					  <view class="line"></view>
				    </view>
					
				  </view>
				  
				  
				  
				 
				  
				</view>
			</view>
		</view>
		<view v-if="tabCur===1">
			<!-- <view class="tabCur1">
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
				  
				 
				</view> -->
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
					url:'/pages/kpdetail1/kpdetail1?id=6509b4c0a09a9bd68b096c54'
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
					url:'/pages/kpdetail3/kpdetail3?id=650aef3a7ad52ddc641579d4'
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
			},
			gojilu8(){
				uni.navigateTo({
					url:'/pages/kpdetail2/kpdetail2?id=6509c570fe975fba5aca897e'
				})
			}
		}
	}
</script>

<style scoped lang="scss">
//顶部导航栏
.line{
  
  float:right;
  width: 100%;
  height: 1px;
  margin-top: -0.5em;
  background:#d4c4c4;
  position: relative;
  text-align: center;
}

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
		  padding-left: 15rpx;
		    padding-left: 15rpx;
		    padding-right: 15rpx;
		    padding-top: 15rpx;
			padding-bottom: 15rpx;
			border-radius: 25rpx;
		  background: #ffaa00;
        font-size: 26rpx;
        font-family: SegoeUI-Bold;
        line-height: 18rpx;
        font-weight: 700;
        color: white;
      }
	  .font_4 {
	    font-size: 26rpx;

	    font-weight: 500;
	    color: #55557f;
	  }
    }
  }
</style>
