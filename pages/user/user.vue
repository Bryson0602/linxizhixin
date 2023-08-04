<template>
  <view class="flex-col page">
    <view class="flex-col flex-auto group">
      <view class="flex-col section space-y-13">
		  
        <view class="flex-row justify-center items-center group_2">
			<image class="image1" src="../../static/plus.png" mode=""></image>
          <view class="flex-col justify-start items-start relative text-wrapper">
            <text class="text">搜索你的好友</text>
          </view>
          <image
            class="image"
            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16908596901104497480.png"
          />
          <image
            class="image_2"
            src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385894443945464.png"
          />
        </view>
		
        <view class="flex-row space-x-14">
          <view class="flex-col justify-start items-center equal-division-item" @click="gopipei" >
            <text class="font_1">智能匹配</text>
          </view>
          <view class="flex-col justify-start items-center relative equal-division-item" >
            <image
              class="image_3 pos"
              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385893796236975.png"
            />
            <text class="relative font_1">我的状态</text>
          </view>
        </view>
      </view>
	  
      <view class="flex-col relative section_2 space-y-11">
        <text class="self-start text_2">消息</text>
		
        <view class="flex-row items-center space-x-14" @click="gochat(item)" v-for="(item, index) in arrList" :key="id">
          <view class="section_3">
			  <image :src="item.url" mode=""></image>
		  </view>
          <view class="flex-col items-start space-y-8">
            <text class="font_2">{{item.name}}</text>
            <text class="font_3">{{item.msg}}</text>
          </view>
        </view>
		 <!-- <view class="flex-row items-center space-x-14">
		   <view class="section_3"></view>
		   <view class="flex-col items-start space-y-8">
		     <text class="font_2">咖啡不苦命苦</text>
		     <text class="font_3">真的假的啊哈哈哈</text>
		   </view>
		 </view>-->

      </view>
    </view>

  </view>
</template>

<script>
  export default {
    components: {},
    data() {
      return {
		  nextname:"",
		  nexturl:"",
		  currentIndex: 0, // 当前要添加的元素在arrList1中的索引
		  arrList: [
		    {
		      id: 1,
		      url: "../../static/tx11.jpeg",
		      name: '新朋友',
		      msg: 'OK',
		    },
		    {
		      id: 2,
		      url: "../../static/tx14.jpeg",
		      name: '好爱笑',
		      msg: '没关系的',
		    },
			{
			  id: 3,
			  url: "../../static/tx12.jpeg",
			  name: '小雨',
			  msg: '明天去哪里玩？',
			},
			{
			  id: 4,
			  url: "../../static/tx15.jpeg",
			  name: '圆圆',
			  msg: '到时候一起去参加活动吧~',
			},
			{
			  id: 5,
			  url: "../../static/tx13.jpeg",
			  name: '若楠',
			  msg: '不见不散哦',
			},
		  ],
		  arrList1: [
		    {
		      id: 6,
		      url: "../../static/tx16.jpeg",
		      name: '小曲奇',
		      msg: '我们已经是好友了，现在可以开始...',
		    },
		    {
		      id: 7,
		      url: "../../static/tx17.jpeg",
		      name: '快乐小猫',
		      msg: '我们已经是好友了，现在可以开始...',
		    },
			{
			  id: 8,
			  url: "../../static/tx18.jpeg",
			  name: '小晨',
			  msg: '我们已经是好友了，现在可以开始...',
			},
			{
			  id: 9,
			  url: "../../static/tx19.jpeg",
			  name: '梦想家',
			  msg: '我们已经是好友了，现在可以开始...',
			},
			{
			  id: 10,
			  url: "../../static/tx20.jpeg",
			  name: '自由飞翔',
			  msg: '我们已经是好友了，现在可以开始...',
			},
		  ],
	  };
    },
    methods: {
		gochat(item){
			console.log(item.name);
			console.log(item.url);
			console.log(item.id);
			uni.navigateTo({
				url:"/pages/chat/chat?name=" + item.name + '&url=' + encodeURIComponent(item.url) + "&id=" + item.id
			})
		},
		gopipei(){
			if (this.currentIndex < this.arrList1.length) {
			const nextElement = this.arrList1[this.currentIndex];
			console.log(nextElement.name);
			this.nextname=nextElement.name
			this.nexturl=nextElement.url
			this.arrList.push(nextElement);
			this.currentIndex++;
		  }
			uni.navigateTo({
				//url:`/pages/pipei/pipei?name=${nextElement.name}`
				url:"/pages/pipei/pipei?name=" + this.nextname + '&url=' + encodeURIComponent(this.nexturl)
			})
		},
		loadData() {
			localStorage.clear();//此处取消缓存
			const storedArrList = localStorage.getItem("arrList");
			if (storedArrList) {
			  this.arrList = JSON.parse(storedArrList);
			}
		},
		  saveData() {
			localStorage.setItem("arrList", JSON.stringify(this.arrList));
		}
	},
	mounted() {
	      this.loadData();
	      window.addEventListener("beforeunload", this.saveData);
	    },
	beforeDestroy() {
	  this.saveData();
	  window.removeEventListener("beforeunload", this.saveData);
	}
  };
</script>

<style scoped lang="scss">
  .page {
	  position: fixed;
    //background-color: #ffffff;
	background-image: linear-gradient(180deg, #ccf0f0 0%, #eff0ff 21.4%, #deecff 48.5%, #eff0ff 76.7%, #ccf0f0 100%);
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .group {
      overflow-y: auto;
      .section {
        padding: 15rpx 48rpx 228rpx;
        //background-color: #65cbc8;
        .group_2 {
          padding: 0 58rpx;
          .text-wrapper {
            margin: 4rpx 0;
            padding: 12rpx 0;
            background-color: #ffffff;
            border-radius: 26rpx;
            box-shadow: 0px 10rpx 8rpx #9695a129;
            width: 450rpx;
            height: 60rpx;
            .text {
			  margin: auto 0;
              margin-left: 44rpx;
              color: #d4d0d0;
              font-size: 20rpx;
              font-family: SegoeUI;
            }
          }
          .image {
            margin-left: 10rpx;
            width: 48rpx;
            height: 48rpx;
          }
		  .image1 {
		    margin-right: 10rpx;
		    width: 48rpx;
		    height: 48rpx;
		  }
          .image_2 {
            margin-left: 20rpx;
            width: 42rpx;
            height: 40rpx;
          }
        }
      }
      .space-y-13 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 26rpx;
        }
      }
      .section_2 {
        margin: -200rpx 40rpx -174rpx;
        padding: 28rpx 26rpx 28rpx;
		height: 100%;
        background-color: #ffffff;
		border-radius: 30rpx;
        background-size: 100% 100%;
        background-repeat: no-repeat;
        .text_2 {
          color: #202020;
          font-size: 40rpx;
          font-family: SegoeUI-Bold;
          font-weight: 700;
          line-height: 37rpx;
		  
        }
      }
      .space-y-11 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 28rpx;
        }
      }
      .space-x-14 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
			
          margin-left: 28rpx;
        }
        .equal-division-item {
          flex: 1 1 314rpx;
          //padding: 96rpx 0 88rpx;
          filter: drop-shadow(0px 6rpx 6rpx #00000029);
		  background-color: #fff0eb;
		  //background-image: linear-gradient(180deg, #ffe4dd 0%, #ffffff 100%);
		  // background: linear-gradient(
		  //     to bottom right, 
		  //     #ffffff 0%,
		  //     #fff6f3 20%,
		  //     #fffaf6 40%,
		  //     #fff5ed 60%,
		  //     #ffefe5 80%,
		  //     #f9dfd2 100%
		  //   );
		  //background-image: url(../../static/xinqiu.jpg);
		  border-radius: 60rpx;
          background-size: 100% 100%;
          background-repeat: no-repeat;
          height: 150rpx;
          .font_1 {
            font-size: 40rpx;
            font-family: SegoeUI;
            //line-height: 120rpx;
			margin: auto auto;
			font-weight: 700;
            color: #535766;
          }
          .image_3 {
            width: 24rpx;
            height: 24rpx;
          }
          .pos {
            position: absolute;
            right: 30rpx;
            top: 24rpx;
          }
        }
        .section_3 {
          background-color: #d4d0d0;
          border-radius: 50%;
          width: 104rpx;
          height: 104rpx;
		  overflow: hidden;
		  image
		  {
			  width: 104rpx;
			  height: 104rpx;
		  }
        }
        .space-y-8 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 16rpx;
          }
          .space-x-8 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 16rpx;
            }
          }
        }

        .font_2 {
          font-size: 32rpx;
          font-family: SegoeUI;
          line-height: 30rpx;
          color: #202020;
        }
        .font_3 {
          font-size: 28rpx;
          font-family: SegoeUI;
          line-height: 26rpx;
          color: #838383;
        }
      }
    }
  }
</style>