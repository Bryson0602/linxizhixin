<template>
	<view class="detail" >		
		<view v-if="loadState">			
			<view class="title">{{detail.title}}</view>
			<view class="info">
				
			</view>
			
			<view class="content">
				<text>{{detail.content1}}</text>
				<image :src="detail.picture1" mode="widthFix"></image>
				<text>{{detail.content2}}</text>
				<image :src="detail.picture2" mode="widthFix"></image>
				<text>{{detail.content3}}</text>
				<image :src="detail.picture3" mode="widthFix"></image>
				<text>{{detail.content4}}</text>
				<image :src="detail.picture4" class="image" mode="widthFix"></image>
				<text>{{detail.content5}}</text>
				<image :src="detail.picture5" mode="widthFix"></image>
				
			</view>
			<!-- <view class="content" v-else>
				<text>{{detail.content1}}</text>
				<image :src="detail.picture1" mode="widthFix"></image>
				<text>{{detail.content2}}</text>
				<image :src="detail.picture2" mode="widthFix"></image>
				<text>{{detail.content3}}</text>
				<image :src="detail.picture3" mode="widthFix"></image>
				<text>{{detail.content4}}</text>
				<image :src="detail.picture4" mode="widthFix"></image>
				<text>{{detail.content5}}</text>
				<image :src="detail.picture5" mode="widthFix"></image>
				
			</view> -->
			<view class="flex-row dz">
				<view class="flex-col items-center">
					<image @click="toggleImage" :src="currentImage" mode=""></image>
					<text>{{num}}</text>
				</view>
				<view class="flex-col items-center">
					<image @click="toggleImage1" :src="currentImage1"  mode=""></image>
					<text>{{num1}}</text>
				</view>
				<view class="flex-col items-center">
					<image src="../../static/fenxiang.png" mode="" @click="goShareClick"></image>
					<cc-shareMenu ref="share" :contentHeight="580" :shareList="shareList" @click="shareMenuClick"></cc-shareMenu>
					<text>33</text>
				</view>	
			</view>
			<!-- <view class="picurls" v-if="detail.picurls && detail.picurls.length">
				<image v-for="item in detail.picurls" :src="item" mode="widthFix"></image>
			</view> -->
			
			<!-- <view class="btnGroup">
				<button size="mini" @click="goEdit">修改</button>
				<button size="mini" type="warn" @click="onRemove">删除</button>
			</view> -->
		</view>
		
		<view v-else>
			<uni-load-more status="loading"></uni-load-more>
		</view>
		
		
	</view>
</template>

<script>
	let id;
	export default {
		data() {
			return {
				set:0,
				shareList: [],
				detail:{},
				loadState:false,
				currentImage: '../../static/dianzan.png',
				image1: '../../static/dianzan.png',
				image2: '../../static/dianzan-xz.png',
				num:223,
				isImage1: true,
				currentImage1: '../../static/shoucang.png',
				image11: '../../static/shoucang.png',
				image21: '../../static/shoucang-xz.png',
				num1:56,
				isImage11: true,
			};
		},
		onLoad(e){			
			id=e.id
			this.set1();
			
		},
		onShow(){
			this.getDetail();
			
		},
		mounted() {
		    this.shareList = [{
		            type: 1,
		            icon: '/static/icon_weixin.png',
		            text: '微信好友'
		        },
		        {
		            type: 2,
		            icon: '/static/icon_pengyouquan.png',
		            text: '朋友圈'
		        },
		        {
		            type: 3,
		            icon: '/static/icon_qq.png',
		            text: 'QQ好友'
		        },
		        {
		            type: 4,
		            icon: '/static/icon_QQkongjian.png',
		            text: 'QQ空间'
		        },
		        {
		            type: 5,
		            icon: '/static/icon_weibo.png',
		            text: '微博'
		        }
		    ];
		},
		methods:{
			set1(){
				this.set=options.e;
			    console.log(this.set)
			},
			goShareClick() {
			    this.$refs.share.toggleMask();
			},
			
			shareMenuClick(name){
			
			    uni.showModal({
			        title: '温馨提示',
			        content:'点击的分享菜单名称是 = ' + name
			    })
			},
			//跳转到修改页面
			// goEdit(){
			// 	uni.navigateTo({
			// 		url:"/pages/edit/edit?id="+id
			// 	})
			// },
			
			//删除一条记录
			// onRemove(){
			// 	uni.showModal({
			// 		content:"是否确认删除？",
			// 		success:res=>{						
			// 			if(res.confirm){
			// 				this.removeFun()
			// 			}
			// 		}					
			// 	})			
				
			// },
			
			// removeFun(){
			// 	uniCloud.callFunction({
			// 		//name:"art_remove_row",
			// 		data:{
			// 			id
			// 		}
			// 	})
			// 	// .then(res=>{
			// 	// 	uni.showToast({
			// 	// 		title:"删除成功~"
			// 	// 	})
			// 	// 	setTimeout(()=>{
			// 	// 		uni.reLaunch({
			// 	// 			url:"/pages/index/index"
			// 	// 		})
			// 	// 	},800)
			// 	// })
			// },
			toggleImage() {
			  this.isImage1 = !this.isImage1;
			  if(this.isImage1===false)
			  {
				  this.num++
				  uni.showToast({
				    title: `点赞成功`,
				    icon: 'none'  
				  })
			  }
			  else{
				  this.num--
			  }
			  this.currentImage = this.isImage1 ? this.image1 : this.image2;
			},
			toggleImage1() {
			  this.isImage11 = !this.isImage11;
			  if(this.isImage11===false)
			  {
				  this.num1++
				  uni.showToast({
					title: `收藏成功`,
					icon: 'none'  
				  })
			  }
			  else{
			  	  this.num1--
			  }
			  this.currentImage1 = this.isImage11 ? this.image11 : this.image21;
			},
			//获取详情
			getDetail(){
				uniCloud.callFunction({
					name:"art_get_row",
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
				// .catch(()=>{
				// 	uni.showToast({
				// 		icon:"error",
				// 		title:"删除有误"
				// 	})
				// 	setTimeout(()=>{
				// 		uni.reLaunch({
				// 			url:"/pages/index/index"
				// 		})
				// 	},800)
					
				// })
			}
		}
		
	}
</script>

<style lang="scss" scoped>
	.image{
		width:665rpx;
	}
	.content {
	    display: flex;
	    flex-direction: column;
	
	}
	.page{
		
	}
.detail{
	padding:30rpx;
	background: #F9F9FE;
	// background-image: linear-gradient(180deg, #ccf0f0 0%, #eff0ff 21.4%, #ffffff 48.5%, #eff0ff 76.7%, #ccf0f0 100%);
	.title{
		font-size: 50rpx;
		color:#000;
		text-align: justify;
		line-height: 1.4em;
	}
	.info{
		
		border-radius: 15rpx;
		padding:20rpx;
		font-size: 25rpx;
		
		display: flex;
		justify-content: space-between;
		margin:40rpx 0;
	}
	.content{
		font-size: 36rpx;
		line-height: 1.7em;
		image{
			padding-top: 50rpx;
			width: 100%;
			display: block;
			margin-bottom:30rpx;
		}
	}
	.dz{		
		margin-left: 45%;
		border: 4rpx solid #d8d8d8; /* 添加蓝色边框样式 */
		border-radius: 30rpx;
		justify-content: space-evenly;
		background-color: #fff;
		image{
			margin-top: 10rpx;
			//margin-right: 15rpx;
			width: 70rpx;
			height: 70rpx;
		}

		text{
			font-size: 16rpx;
			color: #767676;
		}
	}
	.picurls{
		
		image{
			
		}
	}
	.btnGroup{
		padding:50rpx 0;	
		button{
			margin-right: 30rpx;
		}
	}
}
</style>
