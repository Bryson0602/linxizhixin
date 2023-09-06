<template>
	<view class="liu-list">
		<scroll-view class="liu-scroll-left" scroll-y="true" :scroll-with-animation="true"
			:scroll-into-view="scrollIntoView">
			<view class="liu-search" id="TOP">
				<image class="liu-search-img" src="../../static/search.png"></image>
				<input class="liu-input" @input="search" v-model="searchStr" placeholder="灵犀号/手机号" maxlength="50"
					placeholder-class="liu-placeholder" />
			</view>
			
			<view class="total">
			<view v-show="!show" class="card">
				<view class="text">我的灵犀号：2387063291</view>
				<view class="notice">好友通知</view>
				<view class="box">
					<image src="../../../../static/tx1.jpg" class="avatar"></image>
					<view class="asd">
						<view>Smile</view>
						<view class="asd2">灵犀号：1234567890</view>
						<view class="asd3">Hello！我是Smile</view>
					</view>
					<view class="asd1">已同意</view>
				</view>
				<view class="box">
					<image src="../../../../static/tx2.jpg" class="avatar"></image>
					<view class="asd">
						<view>程碗饭</view>
						<view class="asd2">灵犀号：8192759403</view>
						<view class="asd3">Hello！我是程碗饭</view>
					</view>
					<view class="asd1">已同意</view>
				</view>
				<view class="box">
					<image src="../../../../static/tx3.jpg" class="avatar"></image>
					<view class="asd">
						<view>林淮</view>
						<view class="asd2">灵犀号：5874029316</view>
						<view class="asd3">Hello！我是林淮</view>
					</view>
					<view class="asd1">已同意</view>
				</view>
				<view class="box">
					<image src="../../../../static/tx4.jpeg" class="avatar"></image>
					<view class="asd">
						<view>好心情</view>
						<view class="asd2">灵犀号：9876543210</view>
						<view class="asd3">Hello！我是好心情</view>
					</view>
					<view class="asd1">已同意</view>
				</view>
				<view class="notice1">查看更多   ></view>
				
				<view class="notice3">可能想认识的人</view>
				<view class="box">
					<image src="../../../../static/shx.jpg" class="avatar"></image>
					<view class="asd">
						<view>Sunshine</view>
						<view class="asd2">灵犀号：0000000000</view>
						<view class="asd3">Hello！我是Sunshine</view>
					</view>
					<view v-if="status1" class="asd4" @click="add4">添加</view>
					<view v-else class="asd4" >待同意</view>
				</view>
				<view class="box">
					<image src="../../../../static/tutu.jpg" class="avatar"></image>
					<view class="asd">
						<view>涂涂</view>
						<view class="asd2">灵犀号：6890421458</view>
						<view class="asd3">Hello！我是涂涂</view>
					</view>
					<view v-if="status2" class="asd4" @click="add3">添加</view>
					<view v-else class="asd4" >待同意</view>
				</view>
				<view class="box">
					<image src="../../../../static/h1.jpg" class="avatar"></image>
					<view class="asd">
						<view>禾一</view>
						<view class="asd2">灵犀号：8790321263</view>
						<view class="asd3">Hello！我是禾一</view>
					</view>
					<view v-if="status3" class="asd4" @click="add2">添加</view>
					<view v-else class="asd4" >待同意</view>
				</view>
				<view class="box">
					<image src="../../../../static/ih1.jpg" class="avatar"></image>
					<view class="asd">
						<view>i禾一</view>
						<view class="asd2">灵犀号：3890071265</view>
						<view class="asd3">Hello！我是i禾一</view>
					</view>
					<view v-if="status" class="asd4" @click="add1">添加</view>
					<view v-else class="asd4" >待同意</view>
				</view>
				<view class="notice1">查看更多   ></view>
				
			</view>
			</view>
			
			<view v-show="show" class="left-list" v-for="(item,index) of scrollLeftObj" :key="index" :id="index!='#'?index:'BOTTOM'">
				<!-- <view class="left-item-title" v-if="item && item.length">{{index}}</view> -->
				<view class="left-item-card" v-for="(mess,inx) in item" @click.stop="chooseItem(mess)">
					<image :style="'border-radius:'+radius" class="left-item-card-img img-info" :src="mess[imgKey]"
						v-if="mess[imgKey]" @click.stop="preview(mess[imgKey])"></image>
					<view :style="'border-radius:'+radius" class="left-item-card-img" v-else>
						{{mess[nameKey] && mess[nameKey].slice(0,1) || ''}}
					</view>
					<view class="left-item-card-info"
						:style="inx<item.length-1?'border-bottom: solid #F4F4F4 1rpx;':''">
						<view class="left-item-card-name">{{mess[nameKey] || ''}}</view>
						<view class="left-item-card-phone" v-if="mess[phoneKey]">{{mess[phoneKey]}}</view>
						<view v-if="mess[idKey].length<3" class="added">已添加</view>
						<view v-else-if="mess[idKey].length==3 && !isAgreed" class="add" @click="add">添加</view>
						<view v-if="isAgreed" class="addd">待同意</view>
					</view>
				</view>
			</view>
			
			<view class="no-data" v-if="!hasData">
				<image class="no-data-img" src="../../static/noData.png"></image>
				<view class="no-data-name">暂无数据</view>
			</view>
		</scroll-view>
		<view class="liu-scroll-right" v-if="hasData">
			
		</view>
	</view>
</template>

<script>
	import {
		pinyinUtil
	} from './cxy.js';
	export default {
		props: {
			//数据源
			dataList: {
				type: Array,
				required: true,
				default: () => {
					return []
				}
			},
			//显示的主键key值
			idKey: {
				type: String,
				default: 'id'
			},
			//显示的名字key值
			nameKey: {
				type: String,
				default: 'name'
			},
			//显示的电话key值
			phoneKey: {
				type: String,
				default: 'phone'
			},
			//显示的头像key值
			imgKey: {
				type: String,
				default: 'img'
			},
			//头像圆角(rpx、px、%)
			radius: {
				type: String,
				default: '6rpx'
			},
			
		},
		data() {
			return {
				isAgreed: false,
				status:true,
				status1:true,
				status2:true,
				status3:true,
				show:false,
				searchStr: '',
				scrollIntoView: '',
				scrollLeftObj: {},
				oldObj: {},
				scrollRightList: [],
				hasData: true
			};
		},
		watch: {
			dataList: {
				immediate: true,
				deep: true,
				handler(newList) {
					if (newList && newList.length) this.cleanData(newList)
				},
			},
		},
		onLoad:{
			hand(){
				if(event.target.value=='')
				this.show=false
				if(event.target.value.length<10)
					this.show=false
					this.isAgreed=false
				}
			
			
		},
		methods: {
			add2(){
				uni.showToast({
				  title: '等待对方同意中',
				  icon: 'success',
				  duration: 2000
				});
				this.status3=!this.status3
			},
			add3(){
				uni.showToast({
				  title: '等待对方同意中',
				  icon: 'success',
				  duration: 2000
				});
				this.status2=!this.status2
			},
			add4(){
				uni.showToast({
				  title: '等待对方同意中',
				  icon: 'success',
				  duration: 2000
				});
				this.status1=!this.status1
			},
			add1(){
				uni.showToast({
				  title: '等待对方同意中',
				  icon: 'success',
				  duration: 2000
				});
				this.status=!this.status
			},
			add() {
				uni.showToast({
				  title: '等待对方同意中',
				  icon: 'success',
				  duration: 2000
				});
                this.isAgreed = true;
			},
			search() {
				
			
					this.show=true
					if (this.searchStr) {
						let has = false
						this.scrollLeftObj = JSON.parse(JSON.stringify(this.oldObj))
						for (let i in this.scrollLeftObj) {
							this.scrollLeftObj[i] = this.scrollLeftObj[i].filter(item => {
								return (item[this.nameKey].indexOf(this.searchStr) != -1) || item[this.phoneKey]
									.indexOf(this.searchStr) != -1
							})
							if (this.scrollLeftObj[i].length) has = true
						}
						if (has) this.hasData = true
						else this.hasData = false
					} else {
						this.hasData = true
						this.scrollLeftObj = JSON.parse(JSON.stringify(this.oldObj))
					}
				
				
				
			},
			cleanData(list) {
				this.scrollRightList = this.getLetter()
				let newList = []
				list.forEach(res => {
					let initial = pinyinUtil.getFirstLetter(res.name.trim())
					let firsfirs = initial ? initial.substring(0, 1) : ''
					if (!newList[firsfirs]) newList[firsfirs] = []
					newList[firsfirs].push({
						[this.idKey]: res[this.idKey] || '',
						[this.nameKey]: res[this.nameKey].trim() || '',
						[this.phoneKey]: res[this.phoneKey] || '',
						[this.imgKey]: res[this.imgKey] || ''
					})
				})
				this.scrollRightList.forEach(t => {
					if (newList[t]) {
						this.$set(this.scrollLeftObj, t, newList[t])
					} else {
						this.$set(this.scrollLeftObj, t, [])
					}
				})
				let surplusList = []
				for (var i in newList) {
					let han = this.scrollRightList.find(v => {
						return v == i
					})
					if (!han) surplusList.push(newList[i])
				}
				surplusList.forEach(item => {
					this.scrollLeftObj['#'] = this.scrollLeftObj['#'].concat(item)
				})
				this.oldObj = JSON.parse(JSON.stringify(this.scrollLeftObj))
			},
			getLetter() {
				let list = []
				for (var i = 0; i < 26; i++) {
					list.push(String.fromCharCode(65 + i))
				}
				list.push('#')
				return list
			},
			chooseType(item) {
				if (item == '#') item = 'BOTTOM'
				this.scrollIntoView = item
			},
			preview(img) {
				uni.previewImage({
					current: 0,
					urls: [img]
				})
			},
			chooseItem(item) {
				this.$emit('click', item)
			}
		},
	};
</script>
<style>
	/deep/ ::-webkit-scrollbar {
		width: 0;
		height: 0;
		color: transparent;
		display: none;
	}
</style>
<style lang="scss" scoped>
	.asd{
		margin-left: 5%;
		width:50%;
	}
	.asd2{
		margin-top: 1%;
		font-size: 12px;
		color:#919191
	}
	.asd3{
		margin-top: 1%;
		font-size: 11px;
		color:#919191
	}
	.asd1{
		margin-top: 5%;
		margin-left:6%;
		color:#919191
	
	}
	.asd4{
		margin-top: 5%;
		margin-left:3%;
		padding-left: 25rpx;
		padding-right: 25rpx;
		color:#919191;
		widhth:120rpx;
		height:50rpx;
		border: 1px solid #afafaf; 
	}
	.box{
		display:flex;
		padding-bottom:3%;
		padding-top:3%;
		width:100%;
		height:18%;
		background-color: #ffffff;
	}
	.avatar{
		margin-top: 0.5%;
		margin-left:25rpx;
		width:120rpx;
		height:120rpx;
		border-radius: 50%;
	}
	.card{
		
		
		width:100%;
		height:45%;
	}
	.text{
		display: flex;
		margin-left: 28%;
		margin-top: 2%;
		font-size: 14px;
		color:#616161
	}
	.notice{
		background-color:white;
		padding-top: 5%;
		padding-bottom: 5%;
		margin-top:5%;
		padding-left: 5%;
	}
	.notice3{
		background-color:white;
		height:2%;
		font-size:15px;
		padding-top: 5%;
		padding-bottom: 5%;
		margin-top:5%;
		padding-left: 5%;
	}
	.notice1{
		background-color:white;
		padding-bottom: 5%;
		padding-top:5%;
		color:#919191;
		padding-left:40%;
	}
	.total{
		
	}
	.add {
	  position: absolute;
	  top:16%;
	  left:55%;
	  display: inline-block;
	  display: flex;
	  text-align: center;
	  justify-content: center;
	  background-color: #2cbef3;
	  color: #fff;
	  width:25%;
	  padding-top: 1%;
	  
	  height:60rpx;
	  border-radius: 24px;
	  cursor: pointer;
	  margin-right:5% ;
	  margin-bottom: 1%;
	}
	.addd {
	  position: absolute;
	  top:16%;
	  left:55%;
	  display: inline-block;
	  display: flex;
	  text-align: center;
	  justify-content: center;
	  background-color: #71d420;
	  color: #fff;
	  width:25%;
	  padding-top: 1%;
	 
	  height:60rpx;
	  border-radius: 24px;
	  cursor: pointer;
	  margin-right:5% ;
	  margin-bottom: 5%;
	}
	.added {
	  position: absolute;
	  top:16%;
	  left:55%;
	  display: inline-block;
	  display: flex;
	  text-align: center;
	  justify-content: center;
	  background-color: #f3a629;
	  color: #fff;
	  width:25%;
	  padding-top: 1%;
	  
	  height:60rpx;
	  border-radius: 24px;
	  cursor: pointer;
	  margin-right:5% ;
	  margin-bottom: 5%;
	}
	.liu-list {
		width: 100%;
		height: 100vh;
		background-color: #F4F4F4;
		box-sizing: border-box;
		padding-top: 1px;

		.liu-scroll-left {
			height: 100%;

			.liu-search {
				width: 100%;
				height: 106rpx;
				background-color: #FFFFFF;
				display: flex;
				align-items: center;
				justify-content: center;
				position: relative;

				.liu-search-img {
					width: 32rpx;
					height: 32rpx;
					position: absolute;
					left: 64rpx;
				}

				.liu-input {
					width: calc(100% - 64rpx);
					height: 72rpx;
					background: #EEEEEE;
					border-radius: 36rpx;
					padding: 0 32rpx 0 80rpx;
					box-sizing: border-box;
					color: #333333;
				}

				.liu-placeholder {
					color: #777777;
				}
			}

			.left-list {
				height: auto;

				.left-item-title {
					width: calc(100% - 24rpx);
					height: 60rpx;
					padding-left: 24rpx;
					text-align: left;
					line-height: 60rpx;
					font-size: 30rpx;
					color: #666666;
				}

				.left-item-card {
					width: 100%;
					height: 112rpx;
					background-color: #FFFFFF;
					box-sizing: border-box;
					padding-left: 24rpx;
					display: flex;
					align-items: center;
					justify-content: flex-start;

					.left-item-card-img {
						width: 80rpx;
						min-width: 80rpx;
						height: 80rpx;
						background-color: #CFCFCF;
						display: flex;
						align-items: center;
						justify-content: center;
						font-size: 36rpx;
						font-weight: bold;
						color: #FFFFFF;
					}

					.img-info {
						background: none;
						border: solid #f0f0f0 1rpx;
					}

					.left-item-card-info {
						position: relative;
						width: 100%;
						margin-left: 32rpx;
						height: 100%;
						display: flex;
						align-items: flex-start;
						justify-content: center;
						flex-direction: column;

						.left-item-card-name {
							font-size: 30rpx;
							line-height: 30rpx;
							color: #333333;
						}

						.left-item-card-phone {
							margin-top: 14rpx;
							font-size: 28rpx;
							line-height: 28rpx;
							color: #999999;
						}
					}
				}
			}

			.no-data {
				width: 100%;
				display: flex;
				align-items: center;
				justify-items: center;
				flex-direction: column;
				margin-top: 25%;

				.no-data-img {
					width: 200rpx;
					height: 200rpx;
				}

				.no-data-name {
					margin-top: 20rpx;
					font-size: 28rpx;
					color: #666666;
				}
			}
		}

		.liu-scroll-right {
			position: fixed;
			right: 0rpx;
			top: 50%;
			transform: translateY(-47%);
			z-index: 999 !important;
			display: flex;
			align-items: center;
			justify-content: center;
			flex-direction: column;

			.liu-scroll-right-top {
				width: 32rpx;
				height: 32rpx;
				margin-right: 14rpx;
				z-index: 999 !important;
			}

			.liu-scroll-right-name {
				width: 32rpx;
				padding-right: 14rpx;
				height: 28rpx;
				font-size: 22rpx;
				color: #333333;
				line-height: 22rpx;
				margin-top: 8rpx;
				display: flex;
				align-items: center;
				justify-content: center;
			}

			.liu-scroll-right-select {
				padding: 0;
				margin-right: 14rpx;
				width: 28rpx;
				height: 28rpx;
				border-radius: 50%;
				background: #2991FF;
				color: #FFFFFF;
			}
		}
	}
</style>

