<template>
  <view class="container">
    <video class="video-item" src="/assets/video/default.mp4" />

    <view class="detail">
      <text class="detail-text">Video简介：Lorem ipsum dolor sit amet...</text>
    </view>

    <view class="comment-section">
      <label for="input-comment" class="comment-label">评论</label>
      <input id="input-comment" class="comment-input" type="text" placeholder="在这里发表评论…" />

      <view class="icons">
        <button class="icon-btn">👍</button>
        <button class="icon-btn">⭐</button>
      </view>
    </view>
  </view>
</template>


<script>
export default {
  data() {
    return {
    };
  },
  methods: {
  }
};
</script>

<style scoped lang="scss">
/* 视频播放器样式 */
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.video-item {
  height: 300rpx;
  width: 100%;
  object-fit: cover;
}

.detail {
  margin-top: 20rpx;
}

.detail-text {
  text-align: left;
  color: #333;
  font-size: 18rpx;
}

.comment-section {
  width: 100%;
  display: flex;
  flex-direction: column;
  margin-top: 20rpx;
}

.comment-label {
  color: #333;
  font-size: 18rpx;
}

.comment-input {
  height: 40rpx;
  border: none;
  border-bottom: 1rpx solid #333;
  outline: none;
  font-size: 16rpx;
}

.icons {
  display: flex;
  justify-content: space-between;
  margin-top: 10rpx;
}

.icon-btn {
  color: #999;
  font-size: 25rpx;
  background: none;
  border: none;
}
</style>


