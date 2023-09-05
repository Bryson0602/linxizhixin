<template>
	<view class="flex-col page">
	  <view class="flex-col section space-y-20">
	    <view class="flex-row justify-center items-center group space-x-22">
	      <view class="section_2">
			  <image :src="detail.picture" mode=""></image>
		  </view>
	      <view class="flex-col group_2 space-y-18">
	        <view class="flex-col space-y-12">
	          <view class="flex-row items-baseline group_3 space-x-14">
	            <text class="text">{{detail.name}}</text>
	            <text class="text_2">{{detail.job}}</text>
	          </view>
	          <view class="flex-row group_3 space-x-28">
	            <text class="font_1">{{detail.school}}</text>
	            <text class="font_1">{{detail.profession}}</text>
	          </view>
	        </view>
	        <text class="self-start font_1 text_3">{{detail.long}}</text>
	      </view>
	    </view>
	    <view class="flex-row equal-division space-x-8">
	      <view class="flex-col items-center equal-division-item space-y-6">
	        <text class="font_2">{{detail.yuxun}}</text>
	        <text class="font_3">预约量</text>
	      </view>
	      <view class="flex-col items-center equal-division-item space-y-6">
	        <text class="font_2">{{detail.zixun}}</text>
	        <text class="font_3">咨询量</text>
	      </view>
	      <view class="flex-col items-center equal-division-item space-y-6">
	        <text class="font_2">{{detail.guanzhu}}</text>
	        <text class="font_3">关注量</text>
	      </view>
	    </view>
	  </view>
	  <view class="flex-row justify-evenly items-center self-center section_3">
	    <view class="flex-col justify-start"><text class="font_4 text_4">预约咨询</text></view>
	    <view class="flex-col justify-start"><text class="font_5 text_5">学生评价</text></view>
	    <view class="flex-col justify-start"><text class="font_5 text_6">咨询历史</text></view>
	  </view>
	  <view class="flex-col section_4 space-y-36">
		  
	    <view class="flex-row relative">
	      <view class="flex-col justify-start items-center text-wrapper" @click="toggleStatus" :class="status ? 'active' : ''">
			  <text class="font_4" >{{ text }}</text>
		  </view>
	      <view class="flex-col justify-start items-center text-wrapper view" @click="toggleStatus1" :class="status1 ? 'active' : ''">
			  <text class="font_4">{{ text1 }}</text>
		  </view>
	      <view class="flex-row shrink-0 group_4 space-x-30 pos">
	        <view class="flex-col items-center section_5 space-y-18">
	          <text class="font_6">09/08</text>
	          <text class="font_7">周六上午</text>
	        </view>
	        <view class="flex-col items-center section_5 space-y-18">
	          <text class="font_6">09/08</text>
	          <text class="font_7">周六下午</text>
	        </view>
	      </view>
	    </view>
		
	    <view class="flex-row relative">
	      <view class="flex-col justify-start items-center text-wrapper" @click="toggleStatus2" :class="status2 ? 'active' : ''"><text class="font_4">{{ text2 }}</text></view>
	      <view class="flex-col justify-start items-center text-wrapper view_2" @click="toggleStatus3" :class="status3 ? 'active' : ''"><text class="font_4">{{ text3 }}</text></view>
	      <view class="flex-row shrink-0 group_4 space-x-30 pos_2">
	        <view class="flex-col items-center section_5 space-y-18">
	          <text class="font_6">09/09</text>
	          <text class="font_7">周六上午</text>
	        </view>
	        <view class="flex-col items-center section_5 space-y-18">
	          <text class="font_6">09/09</text>
	          <text class="font_7">周六下午</text>
	        </view>
	      </view>
	    </view>
		
		<transition name="fade"><!-- 输入框出现消失动画的衔接 -->
			<view v-show="showInputBox" class="input-box">
				<view class="text">— 咨询预约表单 —</view>
				<view class="form-group">
				  <view class="xyz">
				  	<text class="xy">*</text>
				  	<text class="label">姓名：</text>  
				  </view>
				  <input class="input" v-model="name" placeholder-color="grey" placeholder="请输入姓名" />
				</view>
			    <view class="form-group">
			      <view class="xyz">
			      	<text class="xy">*</text>
			      	<text class="label">电话：</text>  
			      </view>
			      <input class="input" v-model="phone" placeholder="请输入电话" />
			    </view>
				<view class="form-group">
				  <view class="xyz">
				  	<text class="xy">*</text>
				  	<text class="label">心理咨询：</text>  
				  </view>
				  <textarea row="5" class="input"  v-model="phone" placeholder="请简单描述生活中遇到的烦心事"> </textarea>
				</view>
				<view>
					<view class="flex-row justify-evenly" justify-evenly>
					  <button class="button" @click="cancelInput">取消</button>
					  <button class="button" @click="recordNote">提交</button>
					</view>
					
				</view>
				
				<!-- <text class="bj">心理咨询：</text> -->
			  <!-- 输入框 -->
			  <!-- <textarea type="text" v-model="note" /></textarea> -->
			  <!-- <view class="flex-row justify-evenly ">
				  <view class="button" @click="cancelInput">
					  <text>取消</text>
				  </view> -->
				  <!-- 记录按钮 -->
				  <!-- <view class="button" @click="recordNote">
					  <text>记录</text>
				  </view> -->
			 <!-- </view> -->
			</view>
		</transition>
		
	    <view class="flex-row relative">
	      <view class="flex-col justify-start items-center text-wrapper" @click="toggleStatus4" :class="status4 ? 'active' : ''"><text class="font_4">{{ text4 }}</text></view>
	      <view class="flex-col justify-start items-center text-wrapper view_3" @click="toggleStatus5" :class="status5 ? 'active' : ''"><text class="font_4">{{ text5 }}</text></view>
	      <view class="flex-row shrink-0 group_4 space-x-30 pos_3">
	        <view class="flex-col items-center section_5 space-y-18">
	          <text class="font_6">09/10</text>
	          <text class="font_7">周六上午</text>
	        </view>
	        <view class="flex-col items-center section_5 space-y-18">
	          <text class="font_6">09/10</text>
	          <text class="font_7">周六下午</text>
	        </view>
	      </view>
	    </view>
	  </view>
	</view>
</template>

<script>
	let id;
	export default {
		data() {
		  return {
			showInputBox: false,
		    status: false,
		    text: '预约',
			status1: false,
			text1: '预约',
			status2: false,
			text2: '预约',
			status3: false,
			text3: '预约',
			status4: false,
			text4: '预约',
			status5: false,
			text5: '预约',
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
		methods: {
		  //获取详情-----------------------------------------------
		  cancelInput() {//（新增）
		    this.showInputBox = false; // 关闭输入框
		  },
		  recordNote() {//（新增）
		    // 处理记录笔记的逻辑
		    // 记录成功后可以添加一个提示弹窗
		 
		    this.showInputBox = false; 
			
			this.showSuccessModal();// 关闭输入框
		  },
		  showInput() {//（新增）
		    this.showInputBox = true; // 显示输入框
		  },
		  getDetail(){
		  	uniCloud.callFunction({
		  		name:"tea_get_row",
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
		  },
		  toggleStatus() {
			  this.showInputBox = true;
		    this.status = !this.status;
		    if (this.status) {
		      this.text = '已预约';
			   // 调用弹窗方法
			  this.detail.yuxun++
		    } else {
		      this.text = '预约';  
			  this.detail.yuxun--
		    }
		  },
		  toggleStatus1() {
		    this.status1 = !this.status1;
		    if (this.status1) {
		      this.text1 = '已预约';
		  			  this.showSuccessModal(); // 调用弹窗方法
					  this.detail.yuxun++
		    } else {
		      this.text1 = '预约';  
			  this.detail.yuxun--
		    }
		  },
		  toggleStatus2() {
		    this.status2 = !this.status2;
		    if (this.status2) {
		      this.text2 = '已预约';
		  			  this.showSuccessModal(); // 调用弹窗方法
					  this.detail.yuxun++
		    } else {
		      this.text2 = '预约';  
			  this.detail.yuxun--
		    }
		  },
		  toggleStatus3() {
		    this.status3 = !this.status3;
		    if (this.status3) {
		      this.text3 = '已预约';
		  			  this.showSuccessModal(); // 调用弹窗方法
					  this.detail.yuxun++
		    } else {
		      this.text3 = '预约';  
			  this.detail.yuxun--
		    }
		  },
		  toggleStatus4() {
		    this.status4 = !this.status4;
		    if (this.status4) {
		      this.text4 = '已预约';
		  			  this.showSuccessModal(); // 调用弹窗方法
					  this.detail.yuxun++
		    } else {
		      this.text4 = '预约';  
			  this.detail.yuxun--
		    }
		  },
		  toggleStatus5() {
		    this.status5 = !this.status5;
		    if (this.status5) {
		      this.text5 = '已预约';
		  			  this.showSuccessModal(); // 调用弹窗方法
					  this.detail.yuxun++
		    } else {
		      this.text5 = '预约';  
			  this.detail.yuxun--
		    }
		  },
		  showSuccessModal() {
		      uni.showModal({
		        title: '预约成功',
		        content: '您已成功预约!',
		        showCancel: false
		      });
		    }
		}
	}
</script>

<style scoped lang="scss">
	.fade-enter-active,//输入框出现消失动画的衔接
	.fade-leave-active {
	  transition: opacity 0.3s;
	}
	
	.fade-enter,
	.fade-leave-to {
	  opacity: 0;
	}
.page {
    padding-bottom: 96rpx;
    background-color: #ffffff;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .section {
      padding: 55rpx 0 20rpx;
      background-color: #edf2f7;
      .group {
        padding: 0 68rpx;
        .section_2 {
          background-color: #ffffff;
          width: 170rpx;
          height: 170rpx;
		  border-radius: 40rpx;
		  overflow: hidden;
		  image{
			  width: 170rpx;
			  height: 170rpx;
		  }
        }
        .group_2 {
          width: 401rpx;
          .space-y-12 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-top: 24rpx;
            }
            .group_3 {
              padding: 0 4rpx;
              .text {
                color: #000000;
                font-size: 52rpx;
                font-family: SegoeUI-Bold;
                font-weight: 700;
                line-height: 48rpx;
              }
              .text_2 {
                color: #000000;
                font-size: 36rpx;
                font-family: SegoeUI-Bold;
                font-weight: 700;
                line-height: 33rpx;
              }
            }
            .space-x-14 {
              & > view:not(:first-child),
              & > text:not(:first-child),
              & > image:not(:first-child) {
                margin-left: 28rpx;
              }
            }
            .space-x-28 {
              & > view:not(:first-child),
              & > text:not(:first-child),
              & > image:not(:first-child) {
                margin-left: 56rpx;
              }
            }
          }
          .font_1 {
            font-size: 24rpx;
            font-family: SegoeUI;
            line-height: 30rpx;
            color: #000000;
          }
          .text_3 {
            margin-left: 4rpx;
          }
        }
      }
      .space-x-22 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 44rpx;
        }
      }
      .equal-division {
        padding: 0 16rpx;
        .equal-division-item {
          flex: 1 1 238rpx;
          padding: 8rpx 0;
          .font_2 {
            font-size: 24rpx;
            font-family: SegoeUI-Bold;
            line-height: 18rpx;
            font-weight: 700;
            color: #78708c;
          }
          .font_3 {
            font-size: 24rpx;
            font-family: SegoeUI-Bold;
            line-height: 22rpx;
            font-weight: 700;
            color: #78708c;
          }
        }
        .space-y-6 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 12rpx;
          }
        }
      }
      .space-x-8 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 16rpx;
        }
      }
    }
	.input-box {////////////////////////////////////笔记框
	  position: fixed; // 设置为浮动在页面上
	  top: 40%; // 设置在页面中间
	  left: 50%;
	  transform: translate(-50%, -50%);
	  background-color: #fffeea;
	  padding: 20rpx;
	  border-radius: 40rpx;
	  border: 2px solid #ccc;
	  //border: 1rpx solid gray;
	  width: 650rpx; /* 调整输入框的宽度 */
	  //height: 1000rpx;
	  .bj{
		  color: #ffffff;
		  font-size: 45rpx;
		  font-weight: 700;
		  
		  margin-left: 10rpx;
	  }
	  .button {
	    display: inline-block;
	    display: flex;
	    text-align: center;
	    justify-content: center;
	    background-color: #fcc5a0;
	    color: #fff;
	    width:40%;
	    height:80rpx;
	    border-radius: 24px;
	    cursor: pointer;
		line-height: 40px;
	    margin-bottom: 5%;
	  }
	  .button-group {
	    margin-top: 20px;
	    text-align: center;
	  }
	  
	  textarea{
		  margin: 10rpx auto 20rpx;
		  padding:20rpx; /* 设置内边距，增加文字与边框之间的间距 */
		  border-radius: 40rpx;
		  background-color: #f0f0f0;
		  width: 90%; /* 输入框宽度占满输入框容器 */
	      height: 200rpx;
		  color: #78708c;
		  line-height: 1.5;
	  }
	  .bk{
	   background-color: #fff;
	   border-radius: 20rpx;
	   //margin-right: 20rpx;
		 text{
			 font-size: 50rpx;
			 color: #e5e500;
			 margin: auto 40rpx;
		    } 
	    }
	}
    .space-y-20 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 40rpx;
      }
    }
	.input1 {
	  border-radius: 15rpx;
	  height: 180rpx;
	  padding: 0 10px;
	  background-color: #f0f0f0;
	}
	.input {
	  border-radius: 15rpx;
	  height: 80rpx;
	  padding: 0 10px;
	  background-color: #f0f0f0;
	}
    .section_3 {
      margin-top: 30rpx;
      padding: 28rpx 36rpx;
      background-color: #e8f5f4;
      border-radius: 60rpx;
      width: 614rpx;
      .text_4 {
        color: #202020;
      }
	  
      .font_5 {
        font-size: 32rpx;
        font-family: SegoeUI-Bold;
        line-height: 31rpx;
        font-weight: 700;
        color: #707070;
      }
      .text_5 {
        margin: 0 16rpx;
        line-height: 30rpx;
      }
      .text_6 {
        margin: 0 16rpx;
        line-height: 30rpx;
      }
    }
	.xy{
		color:red
	}
	.xyz{
		margin-bottom: 3%;
	}
	.text{
		display:flex;
		align-items: center;
		justify-content: center;
		margin-top: 7%;
		font-weight: bold;
		font-size:35rpx;
		margin-bottom: 5%;
	}
	.label {
	  width: 80px;
	  text-align: right;
	  margin-right: 10px;
	  margin-bottom: 5%;
	}
    .section_4 {
      margin: 24rpx 40rpx 0;
      padding: 36rpx 56rpx 48rpx;
      background-color: #e8f5f4;
      border-radius: 60rpx;
      .text-wrapper {
        flex: 1 1 248rpx;
        padding: 192rpx 0 20rpx;
        background-color: #65cbc8;
        border-radius: 60rpx;
        height: 248rpx;
      }
	  .form-group {
	    display: flex;
	    flex-direction: column;
	    margin-bottom: 20px;
		margin-top: 26rpx;
	  }
	  .active{
			background-color: #b7b0ff;
		}
      .view {
        margin-left: 60rpx;
      }
      .group_4 {
        overflow: hidden;
        height: 180rpx;
        .section_5 {
          margin-bottom: -68rpx;
          flex: 1 1 248rpx;
          padding: 40rpx 0 104rpx;
          background-color: #ffffff;
          border-radius: 60rpx;
          height: 248rpx;
          .font_6 {
            font-size: 40rpx;
            font-family: SegoeUI-Bold;
            line-height: 31rpx;
            font-weight: 700;
            color: #202020;
          }
          .font_7 {
            font-size: 40rpx;
            font-family: SegoeUI-Bold;
            line-height: 37rpx;
            font-weight: 700;
            color: #707070;
          }
        }
      }
      .space-x-30 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 60rpx;
        }
      }
      .pos {
        position: absolute;
        left: 0;
        right: 0;
        top: 0;
      }
      .view_2 {
        margin-left: 60rpx;
      }
      .pos_2 {
        position: absolute;
        left: 0;
        right: 0;
        top: 0;
      }
      .view_3 {
        margin-left: 60rpx;
      }
      .pos_3 {
        position: absolute;
        left: 0;
        right: 0;
        top: 0;
      }
    }
    .space-y-36 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 72rpx;
      }
    }
    .font_4 {
      font-size: 40rpx;
      font-family: SegoeUI-Bold;
      line-height: 37rpx;
      font-weight: 700;
      color: #ffffff;
    }
    .space-y-18 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 36rpx;
      }
    }
  }
</style>
