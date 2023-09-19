<template>
  <view class="flex-col page space-y-26">

    <view class="flex-col space-y-12">
      <view class="flex-col justify-start relative group">
        <view class="flex-col justify-start items-center relative text-wrapper">
          <text class="font_2 text_3" >搜索</text>
        </view>
		
		<view class="flex-col pig content">
		  <view class="flex-col group">
<!-- 		    <image class="self-center tupian" :src="selectedMood1"></image>
			  <image class="self-center tupian" :src="selectedMood2"></image> -->
		    <view class="content">
		      <cc-popup :isShow="isshow1" width="650rpx" height="600rpx" radius="50rpx">
		        <view class="modelContent">
		          <view class="flex-col relative section_2 space-y-10">
		            <view class="flex-row justify-between items-start group_2">
		              <text class="text_10">选择你的心仪导师</text>
		            </view>
		            <view class="grid">
		              <view
		                class="flex-col items-center grid-item space-y-4 image-container"
		                v-for="(emoji, index) in emojiList"
		                :key="index"
		              >
		                <image
		                  class="image xuanting"
		                  :src="emoji.url"
		                  @click="selectMood(emoji, 'isshow1')"
		                />
		                <text class="font_55">{{ emoji.name }}</text>
		              </view>
		            </view>
		          </view>
		        </view>
		        <view class="close" @click="isshow1 = false">✕</view>
		      </cc-popup>
		      <cc-popup :isShow="isshow2" width="650rpx" height="600rpx" radius="50rpx">
		        <view class="modelContent">
		          <view class="flex-col relative section_2 space-y-10">
		            <view class="flex-row justify-between items-start group_2">
		              <text class="text_10">选择你的心仪导师</text>
		            </view>
		            <view class="grid">
		              <view
		                class="flex-col items-center grid-item space-y-4 image-container"
		                v-for="(emoji, index) in emojiList"
		                :key="index"
		              >
		                <image
		                  class="image xuanting"
		                  :src="emoji.url"
		                  @click="selectMood(emoji, 'isshow2')"
		                />
		                <text class="font_55">{{ emoji.name }}</text>
		              </view>
		            </view>
		          </view>
		        </view>
		        <view class="close" @click="isshow2 = false">✕</view>
		      </cc-popup>
		    </view>
		    <!-- <view class="flex-row self-center section_3 space-x-2" @click="isshow1 = true">
		      <text class="font_3 text text_12">换个心情</text>
		    </view>
		    <view class="flex-row self-center section_3 space-x-2" @click="isshow2 = true">
		      <text class="font_3 text text_12">你好啊</text>
		    </view> -->
		  </view>
		</view>
		
        <view class="flex-col section space-y-12 pos">
          <view class="flex-row items-center group_2 space-x-2">
            <image
              class="shrink-0 image"
              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/64c797f95a7e3f03105ee874/6507d195ec886600112812ab/db4bdcd628a556852a6d77909eb192ef.png"
            />
            <text class="font_1 text_2">带你探寻任意两点之间的关系</text>
          </view>
          <view class="flex-row">
            <view class="flex-col justify-start items-center text-wrapper_2" @click="isshow1 = true">
				<text class="font_1">请输入</text>
				<image
				  class="self-center tupian"
				  :src="selectedMood1"
				/>
			</view>
            <image
              class="self-start image_2"
              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/64c797f95a7e3f03105ee874/6507d195ec886600112812ab/9eb3b56110983bd1b41819366ccbd38e.png"
            />
            <image
              class="self-center image_3"
              src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/64c797f95a7e3f03105ee874/6507d195ec886600112812ab/16950135769750850298.png"
            />
            <view class="flex-col justify-start items-center text-wrapper_3" @click="isshow2 = true">
				<text class="font_1">请输入</text>
				<image
				  class="self-center tupian"
				  :src="selectedMood2"
				/>
			</view>
          </view>
          <view class="flex-row justify-between group_3">
            <text class="font_2">A</text>
            <text class="font_2">B</text>
          </view>
        </view>
      </view>
      <view class="flex-row justify-between items-end">
        <view class="flex-col justify-start relative group_5">
          <view class="section_2"></view>
          <text class="text_4 pos_2">每日学习</text>
        </view>
        <view class="flex-row group_4 space-x-10">
          <view class="flex-col justify-start items-center relative text-wrapper_4">
            <text class="font_2 text_5">AI</text>
          </view>
          <view class="flex-col justify-start items-center relative text-wrapper_5">
            <text class="font_1 text_6">心理</text>
          </view>
          <view class="flex-col justify-start items-center text-wrapper_5">
            <text class="font_1 text_7">历史</text>
          </view>
        </view>
      </view>
	  
	  <view  class="item" >
	  	<image @click="tozt1" src="https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/90452b56-9816-44e6-a356-9a6ad2b352de.jpg" mode="widthFix" class="cover"></image>
	  	<view class="info" @click="tozt1">
	  		<view class="font_4">人工智能：未来的引领者</view>
	  		<view class="font_5 ">在科技的海洋中，人工智能（AI）如同一颗璀璨的明珠，以其独特的魅力吸引着全球的目光。</view>
	  	</view>
	  	
	  	<image  @click="tozt2" src="https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/727f6bea-9845-4d34-8991-65b7935377b5.jpeg" mode="widthFix" class="cover"></image>
	  	<view class="info" @click="tozt2">
	  		<view class="font_3">AI发展史：从梦想到现实的跨越</view>
	  		<view class="font_5">从古希腊的神话故事到现代科技的飞速发展，人工智能的发展史可以说是一部人类智慧的历史。</view>
	  	</view>
		<image src="https://mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.cdn.bspapp.com/cloudstorage/9b4fc316-d251-4c6e-ba4f-9fbef099df7f.jpg" mode="widthFix" class="cover"></image>
		<view class="info">
			<view class="font_4">未来心理健康的新视角</view>
			<view class="font_5">在医疗领域，AI的应用也日益广泛，特别是在心理治疗领域，主题将探讨AI与心理治疗的结合及这种结合对未来心理健康的影响。</view>
		</view>
	</view>
	  
	  
     <!-- <view class="flex-col justify-start relative group_6">
        <view class="flex-col justify-start items-center relative text-wrapper_6">
          <text class="font_5">艺术治疗在大学生心理健康教育工作中应用的优势和..</text>
        </view>
        <view class="flex-col space-y-14 pos_3">
          <view class="flex-col section_3 space-y-12" v-for="(item, index) in items" :key="index">
            <view class="flex-col items-start section_4 space-y-4">
				
              <text class="font_4">李克敏谈大学生思想政治教育与心理</text>
              <text class="font_4">健康教育的整合</text>
            </view>
            <text class="font_5 text_8">当前心理问题已经成为困扰大学生学习和生活的重要..</text>
          </view>
        </view>
      </view>
      <view class="section_6"></view> -->
    </view>
  </view>
</template>

<script>
  export default {
    components: {},
    props: {},
    data() {
      return {
      isshow1: false,
      isshow2: false,
      emojiList: [
        { url: '../../static/mr1.png', name: '图灵' },
        { url: '../../static/mr4.png', name: '亚瑟·塞缪尔' },
        { url: '../../static/mr2.png', name: '贾斯汀·卡塞尔' },
        { url: '../../static/mr6.png', name: '山姆·阿尔特曼' },
        { url: '../../static/kxj1.png', name: '艾伦·纽厄尔' },
        { url: '../../static/kxj3.png', name: '杰弗里·辛顿' },
        { url: '../../static/kxj4.png', name: '罗莎琳德·皮卡德' },
        { url: '../../static/kxj5.png', name: '杰里米·拜伦森' },
      ],
      selectedMood1: uni.getStorageSync('selectedMood1') || '',
      selectedMood2: uni.getStorageSync('selectedMood2') || '',
      };
    },

    methods: {
		
	    tozt2(){
	    	uni.navigateTo({
	    		url:'/pages/zt1/zt1'
	    	})
	    },
		tozt1(){
			uni.navigateTo({
				url:'/pages/zt2/zt2'
			})
		},
		selectMood(emoji, popupType) {
		  if (popupType === 'isshow1') {
		    this.selectedMood1 = emoji.url;
		    uni.$emit('updateChartData', emoji.url);
		    uni.setStorageSync('selectedMood1', emoji.url);
		  } else if (popupType === 'isshow2') {
		    this.selectedMood2 = emoji.url;
		    uni.$emit('updateChartData', emoji.url);
		    uni.setStorageSync('selectedMood2', emoji.url);
		  }
		},
		
	},
	created() {
	  this.selectedMood1 = uni.getStorageSync('selectedMood1');
	  this.selectedMood2 = uni.getStorageSync('selectedMood2');
	},
  };
</script>

<style scoped lang="scss">
	.font_55 {
	  font-size: 24rpx;
	  // (32rpx)
	  font-family: SegoeUI-Bold;
	  line-height: 29rpx;
	  font-weight: 700;
	  // color: #1e1c1c;
	  color: #666;
	}
	.tupian{
		border-radius: 50%;
		width: 132rpx;
		height: 132rpx;

		margin-top: -74rpx;
	}
	.font_5{
		font-size: 30rpx;
		font-family: SegoeUI-Bold;
		color:#7d7d7d;
		background-color: white;
		font-weight: 700;
		width:610rpx;
		margin-top: -0.9%;
		margin-left: -3%;
		border-radius:0rpx 0rpx 16rpx 16rpx;
		padding-left: 3%;
		padding-right: 1%;
		padding-bottom: 5px;
	}
	.font_4 {
	  position:absolute;
	  top:-60%;
	  left:13%;
	  font-size: 40rpx;
	  font-family: SegoeUI-Bold;
	  line-height: 48rpx;
	  font-weight: 700;
	  color: #ffffff;
	}
	.font_3 {
	  position:absolute;
	  top:-60%;
	  left:4%;
	  font-size: 40rpx;
	  font-family: SegoeUI-Bold;
	  line-height: 48rpx;
	  font-weight: 700;
	  color: #ffffff;
	}
	.item{
		
		margin: 30rpx 30rpx 0;
		min-height: 200rpx;
		border-radius: 10rpx;
		// box-shadow: 0 6rpx 4rpx 2rpx #F2F2F2;
		
		&:last-child{
			margin-bottom: 30rpx;
		}
		
		.cover{
			width: 100%;
			border-radius: 10rpx 10rpx 0rpx 0rpx;
		}
		
		.info{
			position: relative;
			padding: 0 20rpx 20rpx;
			margin-bottom: 5%;
			.title{
				font-size: 28rpx;
				font-weight: bold;
				margin: 10rpx 0 6rpx;
			}
			.summary{
				color: #777;
				font-size: 24rpx;
			}
		}
	}
	.content {
	      display: flex;
	      flex-direction: column;
	
	  }
	
	//   .popUpBtn {
	//       height: 80rpx;
	//       line-height: 80rpx;
	//       width: 320rpx;
	//       margin-top: 120rpx;
	//       margin-left: auto;
	//       margin-right: auto;
	//       margin-bottom: 50rpx;
	//       background-color: bisque;
	//       text-align: center;
			// background-color: pink;
	//   }
	
	  .modelContent {
	      width: 100%;
	      height: 100%;
	      display: flex;
	      align-items: center;
	      flex-direction: column;
			background-image: linear-gradient(180deg, #ccf0f0 0%, #ebedff 51.5%, #ccf0f0 100%);
			border-radius: 50rpx;
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
	
		 .image-container:hover image {
		            transform: scale(1.3);  
		            transition: all 1s ease 0s;  
		            -webkit-transform: all 1s ease 0s;  
		            -webkit-transform: scale(1.2); /*放大1.3倍*/
					transition-duration: .5s;
					overflow:hidden;
		}
	.page {
	    padding: 36rpx 40rpx 0;
	    background-image: linear-gradient(180deg, #ccf0f0 0%, #ebedff 51.5%, #ccf0f0 100%);
	    width: 100%;
	    overflow-y: auto;
	    overflow-x: hidden;
	    height: 100%;
	    .text {
	      color: #202020;
	      font-size: 48rpx;
	      font-family: SegoeUI-Bold;
	      font-weight: 700;
	      line-height: 44rpx;
	    }
	    .space-y-12 {
	      & > view:not(:first-child),
	      & > text:not(:first-child),
	      & > image:not(:first-child) {
	        margin-top: 24rpx;
	      }
	      .group {
	        padding-top: 50rpx;
	        .text-wrapper {
	          padding: 288rpx 0 24rpx;
	          background-color: #edf1f6;
	          border-radius: 24rpx;
	          box-shadow: 0px 6rpx 8rpx #c3c5ca29;
	          .text_3 {
	            line-height: 30rpx;
	          }
	        }
	        .section {
	          padding: 50rpx 86rpx 32rpx 106rpx;
	          background-color: #ffffff;
	          border-radius: 24rpx 24rpx 0rpx 0rpx;
	          box-shadow: 0px 6rpx 12rpx #c3c5ca29;
	          .group_2 {
	            padding-left: 48rpx;
	            padding-right: 32rpx;
	            .image {
	              width: 80rpx;
	              height: 32rpx;
	            }
	            .text_2 {
	              font-size: 24rpx;
	              line-height: 22rpx;
	            }
	          }
	          .space-x-2 {
	            & > view:not(:first-child),
	            & > text:not(:first-child),
	            & > image:not(:first-child) {
	              margin-left: 4rpx;
	            }
	          }
	          .text-wrapper_2 {
	            padding: 48rpx 0;
	            border-radius: 50%;
	            width: 132rpx;
	            height: 132rpx;
	            border: solid 6rpx #d8d8d8;
	          }
	          .font_1 {
	            font-size: 22rpx;
	            font-family: SegoeUI-Bold;
	            line-height: 20rpx;
	            font-weight: 700;
	            color: #202020;
	          }
	          .image_2 {
	            margin-left: 12rpx;
	            margin-top: 20rpx;
	            width: 176rpx;
	            height: 46rpx;
	          }
	          .image_3 {
	            margin-left: -8rpx;
	            width: 24rpx;
	            height: 24rpx;
	          }
	          .text-wrapper_3 {
	            padding: 48rpx 0;
	            border-radius: 50%;
	            width: 130rpx;
	            height: 130rpx;
	            border: solid 6rpx #d8d8d8;
	          }
	          .group_3 {
	            padding: 0 56rpx;
	          }
	        }
	        .pos {
	          position: absolute;
	          left: 0;
	          right: 0;
	          top: 0;
	        }
	      }
	      .group_5 {
	        padding-top: 28rpx;
	        width: 196rpx;
	        height: 53rpx;
	        .section_2 {
	          background-color: #00aaff;
	          height: 26rpx;
			  border-radius: 5px;
	        }
	        .text_4 {
	          color: #202020;
	          font-size: 44rpx;
	          font-family: SegoeUI-Bold;
	          font-weight: 700;
	          line-height: 41rpx;
	          width: 178rpx;
	        }
	        .pos_2 {
	          position: absolute;
	          left: 50%;
	          top: 0;
	          transform: translateX(-50%);
	        }
	      }
	      .group_4 {
	        margin-right: 22rpx;
	        .text-wrapper_4 {
	          padding: 32rpx 0;
	          background-color:  #89daff ;
	          box-shadow: 0px 6rpx 12rpx #00000029;
	          border-radius: 50%;
	          width: 90rpx;
	          height: 90rpx;
	          .text_5 {
	            color: #78708c;
	          }
	        }
			.text-wrapper_5 {
			          padding: 32rpx 0;
			          background-color: #ffffff;
			          box-shadow: 0px 6rpx 12rpx #00000029;
			          border-radius: 50%;
			          width: 90rpx;
			          height: 90rpx;
			          .font_1 {
			            font-size: 32rpx;
			            font-family: SegoeUI-Bold;
			            font-weight: 700;
			            color: #78708c;
			          }
			          .text_6 {
			            line-height: 28rpx;
			          }
			          .text_7 {
			            line-height: 30rpx;
			          }
			        }
			      }
			      .space-x-10 {
			        & > view:not(:first-child),
			        & > text:not(:first-child),
			        & > image:not(:first-child) {
			          margin-left: 20rpx;
			        }
			      }
			      .font_2 {
			        font-size: 32rpx;
			        font-family: SegoeUI-Bold;
			        line-height: 23rpx;
			        font-weight: 700;
			        // color: #787a8c;
					color: #1e1c1c;
			      }
			      .group_6 {
			        padding-top: 430rpx;
			        .text-wrapper_6 {
			          padding: 356rpx 0 20rpx;
			          background-color: #edf1f6;
			          border-radius: 8rpx;
			          box-shadow: 0px 6rpx 12rpx #c3c5ca29;
			        }
			        .space-y-14 {
			          & > view:not(:first-child),
			          & > text:not(:first-child),
			          & > image:not(:first-child) {
			            margin-top: 28rpx;
			          }
			          .section_3 {
			            padding-bottom: 20rpx;
			            background-color: #edf1f6;
			            border-radius: 8rpx;
			            box-shadow: 0px 6rpx 12rpx #c3c5ca29;
			            .section_4 {
			              padding: 220rpx 12rpx 8rpx;
			              background-color: #ffffff;
			              border-radius: 8rpx;
			              box-shadow: 0px 6rpx 12rpx #c3c5ca29;
			              .font_4 {
			                font-size: 40rpx;
			                font-family: SegoeUI-Bold;
			                line-height: 48rpx;
			                font-weight: 700;
			                color: #787a8c;
			              }
			            }
			            .space-y-4 {
			              & > view:not(:first-child),
			              & > text:not(:first-child),
			              & > image:not(:first-child) {
			                margin-top: 8rpx;
			              }
			            }
			            .text_8 {
			              margin-left: 8rpx;
			            }
			          }
			        }
			        .pos_3 {
			          position: absolute;
			          left: 0;
			          right: 0;
			          top: 0;
			        }
			        .font_5 {
			          font-size: 28rpx;
			          font-family: SegoeUI-Bold;
			          line-height: 26rpx;
			          font-weight: 700;
			          color: #787a8c;
			        }
			      }
			      .section_6 {
			        background-color: #ffffff;
			        border-radius: 8rpx 8rpx 0 0;
			        box-shadow: 0px 6rpx 12rpx #c3c5ca29;
			        height: 102rpx;
			      }
			    }
			  }
			  .space-y-26 {
			    & > view:not(:first-child),
			    & > text:not(:first-child),
			    & > image:not(:first-child) {
			      margin-top: 52rpx;
			    }
			  }
			  .pig {
			  
			    width: 100%;
			    overflow-y: auto;
			    overflow-x: hidden;
			    height: 100%;
				// position: fixed;
			    .group {
			      margin-top: -40rpx;
			      padding: 0 8rpx;
			      
			      .text-wrapper_4 {
			        padding: 52rpx 0 92rpx;
			        // opacity: 0.7;
			        background-image: url('https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385923714170159.png');
			        background-size: 100% 100%;
			        background-repeat: no-repeat;
			        width: 528rpx;
			        .text_9 {
			          margin-left: 32rpx;
			          margin-right: 16rpx;
			          color: #343434;
			          font-size: 44rpx;
			          font-family: SegoeUI-Bold;
			          font-weight: 700;
			          line-height: 42rpx;
			        }
			      }
			      .section_2 {
			        margin: 55rpx auto;
			        padding: 10rpx 0;
			        filter: drop-shadow(0px 6rpx 6rpx #00000029);
			        // background-image: url('https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16892385868940833479.png');
			        background-size: 100% 100%;
			        background-repeat: no-repeat;
			        .group_2 {
			          padding: 0 32rpx;
			          .text_10 {
			            color: #1e1c1c;
			            font-size: 48rpx;
			            font-family: SegoeUI-Bold;
			            font-weight: 700;
			            line-height: 44rpx;
			          }
			          .text_11 {
			  			margin-left: 50rpx;
			            margin-right: 4rpx;
			            margin-top: 28rpx;
			            color: #202020;
			            line-height: 30rpx;
			          }
			        }
			        .grid {
			          padding: 0 14rpx;
			          height: 324rpx;
			          display: grid;
			          grid-template-columns: repeat(4, 1fr);
			          .grid-item {
			            padding: 25rpx 10rpx;
			            .image {
			              width: 115rpx;
			              height: 115rpx;
			  			  border-radius: 50%;
			  			  // 125 125
			            }
			          }
			          .space-y-4 {
			            & > view:not(:first-child),
			            & > text:not(:first-child),
			            & > image:not(:first-child) {
			              margin-top: 8rpx;
			            }
			          }
			        }
			        .font_55 {
			          font-size: 24rpx;
			  		  // (32rpx)
			          font-family: SegoeUI-Bold;
			          line-height: 29rpx;
			          font-weight: 700;
			          // color: #1e1c1c;
			        }
			      }
			      .space-y-10 {
			        & > view:not(:first-child),
			        & > text:not(:first-child),
			        & > image:not(:first-child) {
			          margin-top: 20rpx;
			        }
			      }
			  
			  	  .container {
			  		margin-left: 35rpx;
			  		margin-top: 20rpx;
			  	    display: flex;
			  	    justify-content: center;
			  	    /* other styles */
			  	  }
			  
			  	  // .tupian{
			  	  // 	width: 150rpx;
			  	  // 	height: 150rpx;
			  	  // }
			    }
			  
			    .space-x-8 {
			      & > view:not(:first-child),
			      & > text:not(:first-child),
			      & > image:not(:first-child) {
			        margin-left: 16rpx;
			      }
			    }
			    .font_4 {
			      font-size: 36rpx;
			      font-family: SegoeUI-Bold;
			      line-height: 37rpx;
			      font-weight: 700;
			  	  text-align: center;
			  	  
			    }
			  }
			</style>

