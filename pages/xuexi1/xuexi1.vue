<template>
	<view class="flex-col page space-y-22">
	  
	  <view class="flex-col space-y-10">
	    <view class="flex-row justify-between group_3">
	      <text class="self-start text_5">{{detail.name1}}</text>
	      <view class="flex-col justify-start items-center self-center text-wrapper"@click="showInput"><!-- //（新增方法） -->
	        <text class="font_2 text_4">记笔记</text>
	      </view>
	    </view>
		<!-- 输入框容器，初始时不显示 -->
		<transition name="fade"><!-- 输入框出现消失动画的衔接 -->
			<view v-show="showInputBox" class="input-box">
				<text class="bj">今日笔记：</text>
			  <!-- 输入框 -->
			  <textarea type="text" v-model="note" /></textarea>
			  <view class="flex-row justify-evenly "><!-- 取消按钮 --> 
				  <view class="bk" @click="cancelInput">
					  <text>取消</text>
				  </view>
				  <!-- 记录按钮 -->
				  <view class="bk" @click="recordNote">
					  <text>记录</text>
				  </view>
			  </view>
			</view>
		</transition>
	    <text class="self-start font_2 text_6">就诊科室：{{detail.keshi1}}</text>
	    <view class="flex-col">
	      <view class="flex-col items-start section_2 space-y-4">
	        <text class="font_4">概述：</text>
	        <text class="font_2">{{detail.gaishu1}}</text>
	        
	      </view>
	      <view class="flex-col list space-y-16">
	        <view class="flex-col justify-start items-start list-item" >
	          <view class="group_4">
	            <text class="font_3">定义：</text>
	            <text class="font_2">{{detail.dingyi1}}</text>
	          </view>
	        </view>
			
			<view class="flex-col justify-start items-start list-item" >
			  <view class="group_4">
			    <text class="font_3">就医：</text>
			    <text class="font_2">{{detail.jiuyi1}}</text>
			  </view>
			</view>
			
			<view class="flex-col justify-start items-start list-item" >
			  <view class="group_4">
			    <text class="font_3">治疗：</text>
			    <text class="font_2">{{detail.zhiliao1}}</text>
			  </view>
			</view>
			
			<view class="flex-col justify-start items-start list-item" >
			  <view class="group_4">
			    <text class="font_3">日常：</text>
			    <text class="font_2">{{detail.richang1}}</text>
			  </view>
			</view>
			
	      </view>
	    </view>
	  </view>
	</view>
</template>

<script>
	let id;
	export default {
	  components: {},
	  data() {
	    return {
	      detail:{},
	      loadState:false,
		  showInputBox: false, // 控制输入框的显示与隐藏//（新增）
		  note: '', // 记录输入框的内容//（新增）
	    };
	  },
		onLoad(e){			
			id=e.id
		},
		onShow(){
			this.getDetail();
		},
		methods: {
			showInput() {//（新增）
			  this.showInputBox = true; // 显示输入框
			},
			cancelInput() {//（新增）
			  this.showInputBox = false; // 关闭输入框
			},
			recordNote() {//（新增）
			  // 处理记录笔记的逻辑
			  // 记录成功后可以添加一个提示弹窗
			  uni.showToast({
			    title: `记录完成`,
			    icon: 'none'  
			  })
			  this.showInputBox = false; // 关闭输入框
			},
			//获取详情-----------------------------------------------
			getDetail(){
				uniCloud.callFunction({
					name:"get_Study1_row",
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
		}
	};
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
    padding: 40rpx 40rpx 134rpx;
    background-color: #ffffff;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    //position: fixed;
	.input-box {////////////////////////////////////笔记框
	  position: fixed; // 设置为浮动在页面上
	  top: 50%; // 设置在页面中间
	  left: 50%;
	  transform: translate(-50%, -50%);
	  background-color: #e8d87a;
	  padding: 20rpx;
	  border-radius: 40rpx;
	  //border: 1rpx solid gray;
	  width: 650rpx; /* 调整输入框的宽度 */
	  //height: 1000rpx;
	  .bj{
		  color: #ffffff;
		  font-size: 45rpx;
		  font-weight: 700;
		  margin-left: 10rpx;
	  }
	  textarea{
		  margin: 10rpx auto 20rpx;
		  padding:20rpx; /* 设置内边距，增加文字与边框之间的间距 */
		  border-radius: 40rpx;
		  background-color: #f2f5f7;
		  width: 90%; /* 输入框宽度占满输入框容器 */
	      height: 600rpx;
		  font-size: 50rpx;
		  color: #78708c;
		  line-height: 1.5;
		  
	  }
	  .bk{
	   background-color: #fff;
	   border-radius: 20rpx;
	   //margin-right: 20rpx;
		 text{
			 font-size: 50rpx;
			 color: #c1b365;
			 margin: auto 40rpx;
		    } 
	    }
	}
    .space-y-10 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 20rpx;
      }
      .group_3 {
        padding: 0 6rpx;
        .text_5 {
          //margin-top: 28rpx;
          color: #202020;
          font-size: 60rpx;
          font-family: SegoeUI-Bold;
          font-weight: 700;
          line-height: 84rpx;
        }
        .text-wrapper {
          padding: 24rpx 0;
          background-color: #65cbc8;
          border-radius: 40rpx;
          width: 178rpx;
          height: 74rpx;
          .text_4 {
            color: #ffffff;
            line-height: 29rpx;
          }
        }
      }
      .font_2 {
        font-size: 32rpx;
        font-family: SegoeUI-Bold;
        line-height: 45rpx;
        font-weight: 500;
        color: #78708c;
      }
	  .font_4 {
	    font-size: 32rpx;
	    font-family: SegoeUI-Bold;
	    line-height: 38rpx;
	    font-weight: 700;
	    color: #78708c;
	  }
      .text_6 {
        margin-left: 6rpx;
        color: #202020;
        line-height: 31rpx;
      }
      .section_2 {
		margin-top: 20rpx;
        padding: 28rpx 30rpx 28rpx 30rpx;
        background-color: #edf2f7;
        border-radius: 24rpx;
      }
      .space-y-4 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 8rpx;
        }
      }
      .list {
        padding-top: 36rpx;
        .list-item {
          padding: 28rpx 30rpx 28rpx;
          background-color: #edf2f7;
          border-radius: 24rpx;
          .group_4 {
            //margin-left: 28rpx;
            .font_3 {
              font-size: 48rpx;
              font-family: SegoeUI-Bold;
              line-height: 58rpx;
              font-weight: 700;
              color: #78708c;
            }
          }
        }
      }
      .space-y-16 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 32rpx;
        }
      }
    }
  }
  .space-y-22 {
    & > view:not(:first-child),
    & > text:not(:first-child),
    & > image:not(:first-child) {
      margin-top: 44rpx;
    }
  }
</style>
