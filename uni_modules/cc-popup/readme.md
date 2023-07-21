# cc-popup


#### 使用方法 
```使用方法
	
<view class="popUpBtn" @click="popupClick">
			点击显示弹框</view>

		
<!-- 使用组件 isShow：设置弹框是否显示 width：宽度 height：高度 radius：圆角 -->
		
<cc-popup :isShow='isshow' width="calc(100vw - 70px)" height="346px" radius="16rpx">
			<!-- 自定义展示内容 -->
			<view class="modelContent">

				<view style="margin-top: 6px;">

					弹框标题
				</view>

				<view style="margin-top: 20px; color: #666666; margin: 6px 12px;">

					这是弹框内容 这是弹框内容 这是弹框内容 这是弹框内容
				</view>

				<image class="imageV" :src="mySrc"></image>

				<button style="width: 80%; height: 48px;margin-top: 20px; background-color: seagreen;color: white;"> 确定
				</button>

			</view>
			<!-- 自定义关闭按钮 -->
			<view class="close" @click="isshow=false">✕</view>
		
</cc-popup>

			
					


```

#### HTML代码实现部分
```html

<template>
	<view class="content">


		<view class="popUpBtn" @click="popupClick">
			点击显示弹框</view>

		<!-- 使用组件 isShow：设置弹框是否显示 width：宽度 height：高度 radius：圆角 -->
		<cc-popup :isShow='isshow' width="calc(100vw - 70px)" height="346px" radius="16rpx">
			<!-- 自定义展示内容 -->
			<view class="modelContent">

				<view style="margin-top: 6px;">

					弹框标题
				</view>

				<view style="margin-top: 20px; color: #666666; margin: 6px 12px;">

					这是弹框内容 这是弹框内容 这是弹框内容 这是弹框内容
				</view>

				<image class="imageV" :src="mySrc"></image>

				<button style="width: 80%; height: 48px;margin-top: 20px; background-color: seagreen;color: white;"> 确定
				</button>

			</view>
			<!-- 自定义关闭按钮 -->
			<view class="close" @click="isshow=false">✕</view>
		</cc-popup>

	</view>
</template>

<script>
	export default {
		components: {



		},
		data() {
			return {
				title: 'Hello',
				companyList: [{}, {}, {}],
				isshow: false,
				mySrc: '../../static/apple.jpg'
			}
		},
		onLoad() {

		},
		methods: {

			popupClick() {

				this.isshow = !this.isshow;
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;

	}

	.popUpBtn {
		height: 80rpx;
		line-height: 80rpx;
		width: 320rpx;
		margin-top: 120rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
		background-color: bisque;
		text-align: center;
	}



	.modelContent {
		width: 100%;
		height: 100%;
		display: flex;
		align-items: center;
		flex-direction: column;
	}

	.imageV {

		margin-top: 0px;
		width: calc(100vw - 100px);
		height: calc((100vw - 100px) * 0.567);
	}

	.close {
		width: 60rpx;
		height: 60rpx;
		color: #FFFFFF;
		line-height: 60rpx;
		text-align: center;
		border-radius: 50%;
		border: 1px solid #FFFFFF;
		position: relative;
		bottom: -10%;
		left: 50%;
		transform: translate(-50%, -50%);
	}
</style>


```
