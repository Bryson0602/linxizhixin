<template>
  <view class="news-detail">
    <view class="title">{{title}}</view>
    <view class="info">
      <text class="author">{{author}}</text>
      <text class="time">{{time}}</text>
    </view>

	<text class="time">{{content}}</text>
    <rich-text :nodes="content"></rich-text>

    <view class="image-wrap">
      <image :src="imageUrl" mode="widthFix"></image>
    </view>
  </view> 
</template>

<script>
	let id;
export default {
  data() {
    return {
	  // objData:{},
	  // id:1,
	  
	  detail:{},
	  loadState:false,
	  
      title: '新闻标题新闻标题新闻标题新闻标题新闻标题',
      author: '张三',
      time: '2023-01-01 10:00:00',
      content: '<p>新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文</p>',
      imageUrl: "/static/lb3.jpg"
    };
  },
  onLoad(e){//接受了传过来的id
  	console.log(e)
  	id=e.id
  	this.getDetail();
  },
  methods:{
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
			
		}
  	// getDetail(){
  	// 	// uni.showLoading({
  	// 	// 	title:"数据加载中...",
  	// 	// 	mask:true
  	// 	// })
  	// 	uni.request({
  	// 		url:"https://fc-mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.next.bspapp.com/getArticleSingal/"+this.id,
  	// 		success:res=>{
  	// 			console.log(res)
  	// 			this.objData=res.data.data
  	// 		}
  	// 	})
  	// }
  }
};
</script>

<style scoped lang="scss">
.news-detail{
	padding:30rpx;
	.title {
		font-size: 46rpx;
		color:#333;
		font-weight: bold;
	}

	.info {
	  background: #F6F6F6;
	  padding:20rpx;
	  font-size: 25rpx;
	  color:#666;
	  display: flex;
	  justify-content: space-between;
	  margin:40rpx 0;
	}

	.content {
	  padding-bottom:50rpx;
	  img{
	  	max-width: 100%;
	  }
	}



	.image-wrap {
	  width: 100%;
	}

	image {
	  width: 100%;
	}
}
</style>
