<template>
  <view class="container">
   <!-- <view class="scan-box">
      <image class="scan-line" :src="scanLineSrc"></image>
    </view> -->
    <view class="result" v-if="scanResult">
      <text class="result-text">扫描结果：</text>
      <text class="result-value">{{ scanResult }}</text>
    </view>
    <button class="scan-btn" @click="startScan">扫一扫</button>
  </view>
</template>

<script>
export default {
  data() {
    return {
      scanResult: '',
      scanLineSrc: '@/static/scan-line.png', // 扫码线动画图片路径
      scanTimer: null, // 扫码线动画定时器
    }
  },
  onLoad(){
	this.startScan()  
  },
  methods: {
    startScan() {
      uni.scanCode({
        success: (res) => {
          this.scanResult = res.result;
        },
        fail: (err) => {
          uni.showToast({
            title: '扫码失败',
            icon: 'none'
          });
        }
      });

      // 启动扫码线动画
      this.startScanLineAnimation();
    },
    startScanLineAnimation() {
      let scanBoxHeight = uni.upx2px(300); // 扫码框高度，可根据实际情况调整
      let scanLineHeight = uni.upx2px(2); // 扫码线高度，可根据实际情况调整
      let scanLineTop = 0; // 扫码线初始位置

      this.scanTimer = setInterval(() => {
        scanLineTop += 2;
        if (scanLineTop >= scanBoxHeight - scanLineHeight) {
          scanLineTop = 0;
        }
        this.scanLineSrc = `@/static/scan-line.png?time=${new Date().getTime()}`;
      }, 50);
    },
    stopScanLineAnimation() {
      clearInterval(this.scanTimer);
    }
  },
  beforeDestroy() {
    this.stopScanLineAnimation();
  }
}
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.scan-box {
  position: relative;
  width: 300upx;
  height: 300upx;
  background-color: #000;
  overflow: hidden;
}

.scan-line {
  width: 100%;
  height: 2upx;
  position: absolute;
  top: 0;
  left: 0;
}

.result {
  margin-top: 20upx;
  text-align: center;
}

.result-text {
  font-size: 16upx;
}

.result-value {
  font-size: 14upx;
  color: #333;
  margin-top: 10upx;
}

.scan-btn {
  margin-top: 30upx;
  padding: 10upx 20upx;
  background-color: #007AFF;
  color: #fff;
  border-radius: 4upx;
}
</style>
