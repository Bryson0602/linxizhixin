<template>
<view>
<view>
	<view >
	

		
			<view class="hello">
				HELLO!
			</view>
			
			<view class="welcome">
				欢迎来到灵犀知心
			</view>
			<view class="card">
				<view class="line">
				<button v-show="statue==='second'" class="btn2" @click="onclick2">短信登录</button>
				<button v-show="statue!='second'" class="btn1" @click="onclick2">短信登录</button>
				<button v-show="statue==='first'" class="btn2" @click="onclick1">账号登录</button>
				<button v-show="statue!='first'" class="btn1" @click="onclick1">账号登录</button>
				<button v-show="statue==='third'" class="btn2" @click="onclick3">账号注册</button>
				<button v-show="statue!='third'" class="btn1" @click="onclick3">账号注册</button>
			   	
				</view>
				
			
				
				<view v-show="statue=='first'" >
					<view class="box1">
							<view class="onclick1" >账号</view>
							<input class="text" maxlength="11" type="text"  @blur="onblue" :value="user_name" placeholder="  输入用户名/手机号/邮箱" />
							
					
					
							<view class="onclick1">密码</view>
							<input class="text" maxlength="11" type="password" :value="password" @blur="onpassblue" placeholder="  输入密码（6-12个数字或字母）" />
						
						    <text class="text_6">忘记密码</text>
						      <button class="btn3" @click="login" style="color: white;">登录</button>
						  
								
					</view>
						<view class="box2">
							
					     
						  第三方登录
						 
						</view>
						<view class="box3">
						
					</view>
					<text class="text_">已阅读并同意《用户协议》和《隐私协议》</text>
				</view>
				<view v-show="statue=='second'" >
					<view class="box1">
							<view class="onclick1">手机号</view>
							<input v-on:blur="resname(phone)" class="text" v-model="phone"  maxlength="11" type="text"  placeholder="  请输入手机号" />
							
					
					
							<view class="onclick1">验证码</view>
							<input class="text" maxlength="11" type="password" placeholder="  请输入密码" />
						
						    <text class="text_6">忘记密码</text>
						    <button class="btn3" style="color: white;">登录</button>
								
					</view>
						<view class="box2">
							
					      
						  第三方登录
						
						</view>
						<view class="box3">
						
						
						</view>
						<text class="text_">已阅读并同意《用户协议》和《隐私协议》</text>
						
				</view>
				
				
				<view v-show="statue=='third'" >
					<view class="box1">
							<view class="onclick1" >手机号</view>
							<input class="text" v-on:blur="restname(phone)" maxlength="11" type="text" v-model="phone" placeholder="  请输入手机号" />
							
					
					
							<view class="onclick1" >账号</view>
							<input class="text"  maxlength="11" type="text" v-model="user_name" placeholder="  请输入账号" />
						
						    <view class="onclick1" >密码</view>
						    <input class="text" @blur="respassword(password)" maxlength="11" type="password" v-model="password" placeholder="  请输入密码" />
							
							<view class="onclick1">确认密码</view>
							<input class="text" maxlength="11" type="password" v-model="qpassword" placeholder="  请输入确认密码" />
							
						    
								
					</view>
					
						<button class="btn4" style="color: white;" @click="Register">注册</button>
						
					
						
					</view>
				</view>
				
			</view>
				
		
			
		
		
		
			
	</view>
</view>
</view>
</template>

<script>
	import {  
        mapMutations  
    } from 'vuex';
	
	export default{
		data(){
			return {
				qpassword:"",
				phone:"",
				user_name:"",
				password:"",
				mobile: '',
				tesname: "",
				logining: false,
				statue:'first',
				
			}
		},
		onLoad(){
			
		},
		methods: {
			resname(val) {//用户名输入框失去焦点触发,根据需求使用正则判断
					var regPhone = (/^(13[0-9]|14[1579]|15[0-3,5-9]|16[6]|17[0123456789]|18[0-9]|19[89])\d{8}$/);
					//手机号码正则判断:各运营商开头前三位+八位,即11位的电话号码。
					if (!regPhone.test(val)) {
						// !表示:与regPhone(正则判断)不符
						this.tesname = 1 //标记判断结果,0——正确;1——错误;
						uni.showToast({
							title: '手机号格式错误',
							icon: 'none'
						});
						return;
					}
					if (regPhone.test(val)) {
						this.testname = 0
						uni.showToast({
							title: '手机号格式正确',
						});
						return;
					}
				},
				respassword(val) {//密码输入框失去焦点触发,密码只要不为空就行
					if (val != "") {
						this.tespassword = 0//标记判断结果,0——正确;1——错误;
						return;
					}
					if (val == "") {
						this.tespassword = 1
						uni.showToast({
							title: '密码不能为空',
							icon: 'none'
						});
						return;
					}
				},
			Register(){
				if(this.testname == 0 && this.tespassword == 0&&this.password===this.qpassword){//&&——与符号,表示前后两个条件都要符合才行。
					uni.showToast({
						title: '格式都对',
						
					});
					uniCloud.callFunction({
						name: "register",
						data: {
							"user_name": this.user_name,
							"password": this.password,
							"phone":this.phone
						},
						success: (res) => {
							console.log("对register函数发送请求成功",res)
							var status = res.result.status
							if(status == 0){
								uni.showToast({
									title: '注册成功',
									icon: 'none'
								});
							}else{
								uni.showToast({
									title: '手机号重复',
									icon: 'none'
								});
							}
						},
						fail: (err) => {
							console.log("发送请求失败,错误信息如下",res)
						}
					})
				}else{
					uni.showToast({
						title: '手机号格式不对或确认密码错误',
						icon: 'error'
					});
				}
			},
			restname(val) {//用户名输入框失去焦点触发,根据需求使用正则判断
				var regPhone = (/^(13[0-9]|14[1579]|15[0-3,5-9]|16[6]|17[0123456789]|18[0-9]|19[89])\d{8}$/);
				//手机号码正则判断:各运营商开头前三位+八位,即11位的电话号码。
				if (!regPhone.test(val)) {
					// !表示:与regPhone(正则判断)不符
					this.tesname = 1 //标记判断结果,0——正确;1——错误;
					uni.showToast({
						title: '手机号格式错误',
						icon:"none"
					});
					return;
				}
				if (regPhone.test(val)) {
					this.testname = 0
					uni.showToast({
						title: '手机号格式正确',
					});
					return;
				}
			},
			phonelogin(){
				
			},
			login() {//点击登录触发,格式都对就执行,错就提示
				
					uniCloud.callFunction({
						name: "login",
						data: {
							
							"user_name": this.user_name,
							"password": this.password,
						},
						success: (res) => {
							console.log("对login函数发送请求成功",res)
							var status = res.result.status
							if(status == 0){
								uni.showToast({
									title: '登录成功'
									
								})
								setTimeout(function(){
								uni.navigateTo({
									url:'/pages/liaojie/liaojie'
								})
							},500)
							}if(status == 1){
								uni.showToast({
									title: '用户名不存在',
									icon: 'none'
								});
							}if(status == 2){
								uni.showToast({
									title: '密码错误',
									icon: 'none'
								});
							}
							
						},
						fail: (err) => {
							console.log("发送请求失败,错误信息如下",res)
						}
					})
				
			},
			onclickbout()
			{
				
				uni.request({
					url:"http://localhost:8080/login",
					method:"POST",
					data:{
						username: this.username,
						password: this.password
					},
					
					success: (res)=> {
						if(res.data.flag =='ok'){
							uni.showToast({
								title:'登录成功',
								icon:'success'
							})
							setTimeout(function(){
								uni.switchTab({
									url:"/pages/index/index"
								})
							},100)
							
							console.log(res.data.user);
							window.sessionStorage.setItem("user",res.data.user);
							}
							else{
							uni.showToast({
								title:'用户名或密码错误',
								icon:'none'
							});
						}
					},
					
					fail: ()=>{},
					complete: ()=>{}
				});
			},
			onblue(e)
			{
				console.log(e)
				this.user_name=e.detail.value;
			},
			onpassblue(e)
			{
				this.password=e.detail.value;
			},
			inputChange(e){
				const key = e.currentTarget.dataset.key;
				this[key] = e.detail.value;
			},
			onclick1(){
				
				this.statue='first';
				
			},
			onclick2(){
				this.statue='second';
				
			},
			onclick3(){
				this.statue='third';
				
			},
			navBack(){
				uni.navigateBack();
			},
			toRegist(){
				this.$api.msg('去注册');
			},
			async toLogin(){
				this.logining = true;
				const {mobile, password} = this;
				/* 数据验证模块
				if(!this.$api.match({
					mobile,
					password
				})){
					this.logining = false;
					return;
				}
				*/
				const sendData = {
					mobile,
					password
				};
				const result = await this.$api.json('userInfo');
				if(result.status === 1){
					this.login(result.data);
                    uni.navigateBack();  
				}else{
					this.$api.msg(result.msg);
					this.logining = false;
				}
			}
		},

	}
</script>

<style lang='scss'>
	@font-face {
	  font-family: "阿里妈妈灵动体 VF Thin";src: url("//at.alicdn.com/wf/webfont/2a03Rpk9Yyo5/iMATWg8sXRl2.woff2") format("woff2"),
	  url("//at.alicdn.com/wf/webfont/2a03Rpk9Yyo5/CP47XPEN60Qu.woff") format("woff");
	  font-display: swap;
	}
	.hello{
		margin-top:100rpx;
		margin-left:60rpx;
		font-family: AlimamaAgileVF-Thin;
		font-weight: 1000;
		font-size: xx-large;
		}
		
	page{
		 background-image: linear-gradient(180deg, #ccf0f0 0%, #ebedff 51.2%, #ccf0f0 100%);
	}
	
	
	.icon{
		    
		    display:flex;
		    width:100rpx;
			height:100rpx;
			margin-top:0rpx;
	}
	
	.welcome{
		position:relative;
		padding-top: 100rpx;
		left: 50upx;
		top: -90upx;
		font-size: 46upx;
		color: #555;
		text-shadow: 1px 0px 1px rgba(0,0,0,.3);
	}
	
     .card{
		 margin-top: 28%;
		 display:flex;
		 flex-direction: column;
		 flex: 1;
		 margin-left: 5%;
		 width:90%;
		 height:1300rpx;
		 background: white;
		 border-radius: 50rpx;
	 }
	
	 .box1{
		 width:100%;
		 height:80%;
		 background: white;
		 display:flex;
		 flex-direction: column;
	 }
	 .box2{
		 width:100%;
		 height:5%;
		 margin-left: 40%;
		 display:flex;
		  color: #d5d5d5;
		 margin-top:7%
	 }
	 .box3{
		     justify-content: space-around;
	 		 width:100%;
			 height:5%;
	 		 display:flex;
	 		 background: white;
			 margin-top:10%
	 }
	 
	 .text{
		 margin-top: 0%;
		 margin-left:13%;
		 background-color: #f2f2f2;
		 height:100rpx;
		 margin-right:9%;
		 border-radius: 30rpx;
	 }
	 .onclick1{
		margin-top: 10%; 
		margin-left:14%;
		font-size: 46upx;
		color: #555;
		text-shadow: 1px 0px 1px rgba(0,0,0,.3);
	 }
    .line{
		border-style:none;
		margin-left:3%;
		margin-top: 5%;
		display:flex;
		border-radius: 50rpx;
		width:95%;
		height:6.5%;
		background-color: #eaeaea;
		box-shadow: 0px 6rpx 12rpx #00000029;
	}
	.text_ {
	  margin-left:30%;
	  color: #b8b8b8;
	  font-size: 20rpx;
	  font-family: SegoeUI;
	  line-height: 19rpx;
	}
	.btn1{
		border-style:none;
		width:32%;
		border-radius: 50rpx;
		background-color: #eaeaea;
		font-size: 35rpx;
		font-weight: 700;
	}
	.btn2{
		border-style:none;
		color: #202020;
		width:32%;
		font-size: 35rpx;
		border-radius: 50rpx;
		font-weight: 700;
		box-shadow: 0px 6rpx 12rpx #00000029;
	}
	.btn3{
		margin-top:12%;
		font-size: 44rpx;
		font-family: SegoeUI-Bold;
		font-weight: 700;
		width: 476rpx;
		height:105rpx;
		
		border-radius: 50rpx;
		background: #65cbc8;

	}
	.text-wrapper_4 {
	  margin-top: 30%;
	  margin-left:13%;
	  margin-top: 64rpx;
	  padding: 32rpx 0 28rpx;
	  background-color: #65cbc8;
	  border-radius: 48rpx;
	  width: 476rpx;
	  
	  .text_7 {
	    color: #f6f6f6;
		margin-left:38%;
	    font-size: 44rpx;
	    font-family: SegoeUI-Bold;
	    font-weight: 700;
	    line-height: 40rpx;
	  }
	}
	.text_6 {
	  margin-top: 3%;
	  font-size: 30rpx;
	  margin-left: 480rpx;
	  color: #202020;
	}
	.btn4{
		
		margin-top:12%;
		font-size: 44rpx;
		font-family: SegoeUI-Bold;
		font-weight: 700;
		width: 476rpx;
		height:105rpx;
		border-radius: 50rpx;
		background: #65cbc8;
	
	}
</style>
