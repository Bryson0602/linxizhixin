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
export default {
  data() {
    return {
      title: '新闻标题新闻标题新闻标题新闻标题新闻标题',
      author: '张三',
      time: '2023-01-01 10:00:00',
      content: '<p>新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文新闻正文</p>',
      imageUrl: "/static/lb3.jpg"
    };
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
