<template>
	<view class="detail" >		
		<view v-if="loadState">			
			<view class="title">{{detail.title}}</view>
			<view class="info">
				<text>{{detail.author}}</text>
				<text>			
					<uni-dateformat 
					:date="detail.posttime" 
					format="yyyy年MM月dd日 hh:mm:ss" 
					></uni-dateformat>
				</text>
			</view>
			<view class="content">
				{{detail.content}}
			</view>
			
			<view class="picurls" v-if="detail.picurls && detail.picurls.length">
				<image v-for="item in detail.picurls" :src="item" mode="widthFix"></image>
			</view>
			
			<view class="btnGroup">
				<button size="mini" @click="goEdit">修改</button>
				<button size="mini" type="warn" @click="onRemove">删除</button>
			</view>
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
		methods:{
			//跳转到修改页面
			goEdit(){
				uni.navigateTo({
					url:"/pages/edit/edit?id="+id
				})
			},
			
			//删除一条记录
			onRemove(){
				uni.showModal({
					content:"是否确认删除？",
					success:res=>{						
						if(res.confirm){
							this.removeFun()
						}
					}					
				})			
				
			},
			
			removeFun(){
				uniCloud.callFunction({
					name:"art_remove_row",
					data:{
						id
					}
				}).then(res=>{
					uni.showToast({
						title:"删除成功~"
					})
					setTimeout(()=>{
						uni.reLaunch({
							url:"/pages/index/index"
						})
					},800)
				})
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
				}).catch(()=>{
					uni.showToast({
						icon:"error",
						title:"删除有误"
					})
					setTimeout(()=>{
						uni.reLaunch({
							url:"/pages/index/index"
						})
					},800)
					
				})
			}
		}
		
	}
</script>

<style lang="scss" scoped>
	.page{
		
	}
.detail{
	padding:30rpx;
	background-image: linear-gradient(180deg, #ccf0f0 0%, #eff0ff 21.4%, #ffffff 48.5%, #eff0ff 76.7%, #ccf0f0 100%);
	.title{
		font-size: 50rpx;
		color:#000;
		text-align: justify;
		line-height: 1.4em;
	}
	.info{
		font-size: 30rpx;
		color:#666;
		padding:30rpx 0 60rpx;
		text{
			padding-right: 30rpx;
		}
	}
	.content{
		font-size: 36rpx;
		line-height: 1.7em;
		
		
	}
	.picurls{
		padding-top: 50rpx;
		image{
			width: 100%;
			display: block;
			margin-bottom:30rpx;
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
