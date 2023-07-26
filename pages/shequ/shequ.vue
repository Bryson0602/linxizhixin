<template>
	<view class="flex-col page">
		<view class="status_bar">
		    <!-- 这里是状态栏 -->
		</view>
		
		<view class="ct_tab">
			<view class="ct_item" :class="{'ct_active' : 0 == tabCur}" @click="clickCtTab(0)">
				<text>活动</text>
			</view>
			<view class="ct_item" :class="{'ct_active' : 1 == tabCur}" @click="clickCtTab(1)">
				<text>学习</text>
			</view>
			<view class="ct_item" :class="{'ct_active' : 2 == tabCur}" @click="clickCtTab(2)">
				<text>预约</text>
			</view>
		</view>
		
		<view v-if="tabCur===0">
			<view class="tabCur1">
				<view class="flex-col flex-auto group">
				  <view class="flex-col">
				    <view class="flex-col section_3 view_3 space-y-26">
				      <view class="flex-row justify-between items-center group_3">
				        <view class="flex-row items-baseline space-x-20">
				          <text class="text_2">报名</text>
				          <text class="font_2 text_3">部落</text>
				        </view>
				        <text class="font_2 text_4" @click="gorili">活动日历</text>
							  <image class="dinwei" src="/static/rili.png" mode="heightFix"></image>
				      </view>
							
						
				      <view class="flex-row items-center space-x-8" @click="gogfhd1">
				        <view class="flex-col justify-start items-end section_4">
							<image src="../../static/lb3.jpg" mode=""></image>
				          <view class="flex-col justify-start items-center text-wrapper_2 gf">
							  <text class="font_3">官方</text>
						  </view>
				        </view>
				        <view class="flex-col flex-auto space-y-8">
				          <text class="self-start font_2">心理知识大讲堂</text>
				          <view class="flex-row space-x-10">
				            <view class="flex-col justify-start items-center text-wrapper_3">
				              <text class="font_4">需签到</text>
				            </view>
				            <view class="flex-col justify-start text-wrapper_4"><text class="font_5 text_5">报名审核</text></view>
				          </view>
				          <view class="flex-row justify-between items-center">
				            <view class="group_4">
				              <text class="font_6">可报名20人</text>
<!-- 				              <text class="font_7 text_6">20人</text> -->
				            </view>
				            <text class="font_7 text_7">2023.09.08-2023.09.15</text>
				          </view>
				        </view>
				      </view>
				    </view>
						  
						  
				    <view class="flex-row section_3 space-x-8" @click="gogfhd2">
				      <view class="flex-col justify-start items-end self-center section_4">
						  <image src="../../static/lb4.jpg" mode=""></image>
				        <view class="flex-col justify-start items-center text-wrapper_2 gf"><text class="font_3">官方</text></view>
				      </view>
				      <view class="flex-col flex-auto self-start group_5 space-y-8">
				        <text class="self-start font_2">校园线下心理疏导课堂志愿者</text>
				        <view class="flex-row space-x-10">
				          <view class="flex-col justify-start items-center text-wrapper_3"><text class="font_4">需签到</text></view>
				          <view class="flex-col justify-start text-wrapper_4"><text class="font_5 text_5">报名审核</text></view>
				        </view>
				        <view class="flex-row justify-between items-center">
				          <text class="font_6">不限人数</text>
				          <text class="font_7 text_8">长期报名</text>
				        </view>
				      </view>
				    </view>
						  
				    <view class="flex-row section_3 space-x-8" v-for="item in listArr" :key="item._id" @click="gohuodong(item._id)">
				      <view class="flex-col justify-start items-end self-center section_4">
						  <image :src="item.picture1" mode="aspectFill"></image>
				        <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_3">推荐</text></view>
				      </view>
				      <view class="flex-col flex-auto self-start group_6">
				        <text class="self-start font_2">{{item.title}}</text>
				        <view class="flex-col justify-start items-center self-start text-wrapper_5">
				          <text class="font_4">需签到</text>
						  
				        </view>
						
				        <view class="flex-row justify-between items-center group_7">
				          <text class="font_6">{{item.people}}</text>
				          <text class="font_7 text_8">{{item.actBtime}}</text>
				        </view>
				      </view>
				    </view>
					
				  </view>
				 <!-- <view class="section_7"></view> -->
				</view>
			</view>
		</view>
		
		<view v-else-if="tabCur===1">
			<view class="tabCur1">
				<view class="flex-row justify-between relative page1">
				  <view class="flex-col pos">
				    <view class="flex-col group space-y-19">
				      <view class="flex-row justify-between items-center group_2">
				        <view class="flex-row items-baseline space-x-16">
				          <text class="font_2 text_4">最新</text>
				          <text class="font_3 text_5">最热</text>
				        </view>
				        <view class="flex-col justify-start items-center button"><text class="font_3 text_6">知识科普</text></view>
				      </view>
				      <view class="flex-col space-y-13">
				        <view class="flex-col justify-start items-center self-start button_2">
				          <text class="font_2">知识科普</text>
				        </view>
						
						
						<view class="flex-row justify-between section_5"v-for="item in listArr3" :key="item._id">
						  <view class="flex-col justify-start items-start relative group_4 group_5"@click="goxuexi2(item._id)">
						    <view class="section_6"></view>
						    <view class="flex-col justify-start items-center text-wrapper_3 pos_11">
						      <text class="font_4 text_8">{{item.name}}</text>
						    </view>
						  </view>
						  <view class="flex-col justify-start items-start relative group_4 group_5"@click="goxuexi3(item._id)">
						    <view class="section_6"></view>
						    <view class="flex-col justify-start items-center text-wrapper_3 pos_12">
						      <text class="font_4">{{item.name1}}</text>
						    </view>
						  </view>
						</view>
						
				        
						
				        <view class="flex-col justify-start items-center self-start button_2">
				          <text class="font_2">心理疾病</text>
				        </view>
						
						
				        <view class="flex-row justify-between section_5" v-for="item in listArr2" :key="item._id">
				          <view class="flex-col justify-start items-start relative group_4"@click="goxuexi(item._id)">
				            <view class="section_6"></view>
				            <view class="flex-col justify-start items-center text-wrapper_3 pos_11">
				              <text class="font_4 text_8">{{item.name}}</text>
				            </view>
				          </view>
				          <view class="flex-col justify-start items-start relative group_4"@click="goxuexi1(item._id)">
				            <view class="section_6"></view>
				            <view class="flex-col justify-start items-center text-wrapper_3 pos_12">
				              <text class="font_4">{{item.name1}}</text>
				            </view>
				          </view>
				        </view>
						
						
						
						<view class="flex-row justify-between section_5">
						  <view class="flex-col justify-start items-start relative group_4"@click="goxuexi">
						    <view class="section_6"></view>
						    <view class="flex-col justify-start items-center text-wrapper_3 pos_11">
						      <text class="font_4 text_8">蝴蝶效应</text>
						    </view>
						  </view>
						  <view class="flex-col justify-start items-start relative group_4"@click="goxuexi1">
						    <view class="section_6"></view>
						    <view class="flex-col justify-start items-center text-wrapper_3 pos_12">
						      <text class="font_4">鳄鱼法则</text>
						    </view>
						  </view>
						</view>
						
				        
					  </view>
				    </view>
				  </view>
				</view>
			</view>
		</view>

		<view v-else-if="tabCur===2">
			<view class="tabCur1">
				<view class="flex-col page2">
				  <view class="flex-col group space-y-19">
				    <view class="flex-col space-y-24">
						
				      <view class="flex-row justify-between items-center group_4">
				        <view class="flex-row items-baseline space-x-20">
				          <text class="font_2 text_2">综合排序</text>
				          <text class="font_3 text_3">筛选</text>
				        </view>
				        <view class="flex-col justify-start items-center text-wrapper">
				          <text class="font_3 text_4">我的预约</text>
				        </view>
				      </view>
					  
				      <view class="flex-col space-y-14">
				        <view class="flex-row items-center list-item space-x-14" v-for="item in listArr1" :key="item._id"  @click="goyuyue(item._id)">
				          <view class="shrink-0 section_2">
							<image :src="item.picture" mode=""></image>
						  </view>
				          <view class="flex-col flex-auto space-y-9">
				            <view class="flex-row justify-between items-start">
				              <view class="flex-row items-baseline group_5 space-x-8">
				                <text class="font_5">{{item.name}}</text>
				                <text class="font_2">{{item.job}}</text>
				              </view>
				              <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_4">预约</text></view>
				            </view>
				            <view class="flex-row space-x-12">
				              <text class="font_6">{{item.school}}</text>
				              <text class="font_6">{{item.profession}}</text>
				            </view>
				            <text class="self-start font_6">{{item.short}}</text>
				            <view class="flex-row group_6">
							  <image class="shizhong" src="../../static/shizhong.png" mode="heightFix"></image>
				              <!-- <view class="section_3"></view> -->
				              <text class="font_7 text_5">预约咨询（多点）</text>
				              <view class="section_3"></view>
				            </view>
				          </view>
				        </view>
				      </view>
					  
				    </view>
				  </view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tabCur:0,
				listArr:[],//活动
				listArr1:[],//预约
				listArr2:[],//学习疾病
				listArr3:[],//常识科普
			}
		},
		methods: {
			clickCtTab(ctCur){
				this.tabCur  = ctCur
				console.log(this.tabCur )
			},
			gogfhd1(){
				uni.navigateTo({
					url:"/pages/gfhd1/gfhd1"
				})
			},
			gogfhd2(){
				uni.navigateTo({
					url:"/pages/gfhd2/gfhd2"
				})
			},
			gohuodong(e){
				uni.navigateTo({
					url:"/pages/huodong/huodong?id="+e
				})
			},
			goxuexi(e){
				uni.navigateTo({
					url:"/pages/xuexi/xuexi?id="+e
				})
			},
			goxuexi1(e){
				uni.navigateTo({
					url:"/pages/xuexi1/xuexi1?id="+e
				})
			},
			goxuexi2(e){
				uni.navigateTo({
					url:"/pages/xuexi2/xuexi2?id="+e
				})
			},
			goxuexi3(e){
				uni.navigateTo({
					url:"/pages/xuexi3/xuexi3?id="+e
				})
			},
			goyuyue(e){
				uni.navigateTo({
					url:"/pages/yuyue/yuyue?id="+e
				})
			},
			gorili(){
				uni.navigateTo({
					url:'/pages/rili/rili'
				})
			},
			//获取网络数据
			getData(){
				uni.request({
					url:"https://fc-mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.next.bspapp.com/getActivities",
					success:res=>{
						console.log(res);
						this.listArr=res.data.data
					}
				})
			},
			//获取网络数据-预约
			getData1(){
				uni.request({
					url:"https://fc-mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.next.bspapp.com/getTeacherAll",
					success:res=>{
						console.log(res);
						this.listArr1=res.data.data
					}
				})
			},
			//获取网络数据-学习疾病
			getData2(){
				uni.request({
					url:"https://fc-mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.next.bspapp.com/getStudy1All",
					success:res=>{
						console.log(res);
						this.listArr2=res.data.data
					}
				})
			},
			//获取网络数据-知识科普
			getData3(){
				uni.request({
					url:"https://fc-mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.next.bspapp.com/get_Study2_All",
					success:res=>{
						console.log(res);
						this.listArr3=res.data.data
					}
				})
			}
		},
		onLoad(){
			this.getData();
			this.getData1();
			this.getData2();
			this.getData3();
		}
	}
</script>


<style scoped lang="scss">
//顶部导航栏
.ct_tab{
	width: 100%;
	margin: 0 auto;
	padding: 15rpx 0;
	font-size: 45rpx;
	font-weight: bold;
	color: #c0c8d0;
	background: #edfeff;
	display: flex;
	justify-content: space-evenly;
	align-items: center;
}
.ct_item{
	//width: 20%;
	padding-bottom: 15rpx;
}
.ct_item text{//小横杠字体距离
	padding: 5rpx 0;
	
}
.ct_active{
	color: #000000;//字体颜色
}
.ct_active text{
	//小横杠
	border-bottom: 5px solid #65cbc8;
	
}
.tabCur1{
	//padding: 20rpx;
	//background: #007AFF;
	color: #aa55ff;
	//margin-top: 10rpx;
}
//-------------------------------------------------------------------------------
.page {//活动page
	position: fixed;
    background-color: #ebebeb;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .group {
      overflow-y: auto;
      .section_3 {
        margin-top: 20rpx;
        padding: 28rpx 32rpx 24rpx 40rpx;
        background-color: #ffffff;
        .group_3 {
          padding: 0 0rpx;
		  .dinwei{
		  	height: 45rpx;
		  }
          .space-x-20 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 40rpx;
            }
            .text_2 {
              color: #202020;
              font-size: 32rpx;
              font-family: SegoeUI-Bold;
              font-weight: 700;
              line-height: 30rpx;
            }
            .text_3 {
              color: #b4b4b4;
            }
          }
          .text_4 {
			margin-left: 345rpx;
            margin-right: 0rpx;
            color: #707070;
          }
        }
        .group_5 {
          margin-top: 20rpx;
        }
        .group_6 {
          margin-top: 20rpx;
        }
        .text_8 {
          line-height: 28rpx;
        }
        .text-wrapper_6 {
          padding: 20rpx 0 108rpx;
          background-color: #707070;
          border-radius: 24rpx;
          width: 196rpx;
          height: 146rpx;
          .font_8 {
            font-size: 20rpx;
            font-family: SegoeUI-Bold;
            line-height: 18rpx;
            font-weight: 700;
            color: #707070;
          }
          .text_9 {
            margin-right: 24rpx;
          }
        }
        .group_8 {
          margin-top: 20rpx;
        }
        .group_9 {
          margin-top: 20rpx;
        }
      }
      .view_3 {
        margin-top: 0;
      }
      .space-y-26 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 52rpx;
        }
      }
      .space-x-8 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 16rpx;
        }
      }
      .section_4 {
        //padding: 12rpx 0 102rpx;
        background-color: #707070;
        border-radius: 24rpx;
        width: 196rpx;
        height: 146rpx;
		overflow: hidden;
		position: relative;//相
		
		image{
			width: 196rpx;
			height: 146rpx;
		}
        .text-wrapper_2 {
		  position: absolute;//绝
		  right: 10rpx;
		  top: 10rpx;
          //margin-right: 10rpx;
          padding: 8rpx 0;
          background-color: #ff8323;
          border-radius: 60rpx;
          width: 68rpx;
          .font_3 {
            font-size: 20rpx;
            font-family: SegoeUI-Bold;
            line-height: 18rpx;
            font-weight: 700;
            color: #ffffff;
          }
        }
		.gf{
			background-color: #00aaff;
		}
      }
      .space-x-10 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 20rpx;
        }
        .text-wrapper_3 {
          padding: 8rpx 0;
          background-color: #ffe7d4;
          border-radius: 60rpx;
          width: 114rpx;
          height: 38rpx;
        }
        .text-wrapper_4 {
          padding: 8rpx 0;
          background-color: #d6f4ff;
          border-radius: 60rpx;
          height: 38rpx;
          .font_5 {
            font-size: 28rpx;
            font-family: SegoeUI-Bold;
            line-height: 26rpx;
            font-weight: 700;
            color: #00bbff;
          }
          .text_5 {
            margin-left: 16rpx;
            margin-right: 8rpx;
          }
        }
      }
      .font_7 {
        font-size: 24rpx;
        font-family: SegoeUI;
        line-height: 26rpx;
        color: #707070;
      }
      .font_4 {
        font-size: 28rpx;
        font-family: SegoeUI-Bold;
        line-height: 26rpx;
        font-weight: 700;
        color: #ff8323;
      }
      .section_5 {
        margin-top: 20rpx;
        padding: 28rpx 32rpx 0 40rpx;
        background-color: #ffffff;
        .section_6 {
          background-color: #707070;
          border-radius: 24rpx;
          width: 196rpx;
          height: 146rpx;
        }
        .group_10 {
          margin-top: 8rpx;
          .view_4 {
            margin-top: 32rpx;
          }
        }
      }
      .font_2 {
        font-size: 28rpx;
        font-family: SegoeUI-Bold;
        line-height: 30rpx;
        font-weight: 700;
        color: #202020;
      }
      .text-wrapper_5 {
        margin-top: 20rpx;
        padding: 8rpx 0;
        background-color: #ffe7d4;
        border-radius: 60rpx;
        width: 114rpx;
      }
      .group_7 {
        padding-top: 12rpx;
        .text_10 {
          line-height: 28rpx;
        }
      }
      // .section_7 {
      //   margin: 44rpx 0 -180rpx;
      //   background-color: #ffffff;
      //   height: 122rpx;
      // }
    }
    
    .space-y-8 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 16rpx;
      }
      .group_4 {
        line-height: 22rpx;
        height: 22rpx;
        .text_6 {
          line-height: 22rpx;
        }
      }
      .text_7 {
        line-height: 28rpx;
      }
    }
    .font_6 {
      font-size: 24rpx;
      font-family: SegoeUI-Bold;
      line-height: 22rpx;
      font-weight: 700;
      color: #707070;
    }
	
	
//-------------------------------------------------------------------------------
	.page1 {//学习page1
	position: fixed;
    padding: 48rpx 152rpx 1740rpx 156rpx;
    background-color: #ffffff;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .pos {
      position: absolute;
      left: 0;
      right: 0;
      top: 20rpx;//改40
      
      .group {
        padding: 15rpx 40rpx 64rpx;
        .group_2 {
          padding: 0 10rpx;
          .space-x-16 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 32rpx;
            }
            .text_4 {
              color: #202020;
            }
            .text_5 {
              color: #b4b4b4;
            }
          }
          .button {
            padding: 16rpx 0;
            background-color: #65cbc8;
            border-radius: 60rpx;
            //box-shadow: 0px 6rpx 12rpx #00000029;
            width: 150rpx;
            height: 54rpx;
            .text_6 {
              color: #fafafa;
            }
          }
          .font_3 {
            font-size: 28rpx;
            font-family: SegoeUI-Bold;
            line-height: 26rpx;
            font-weight: 700;
          }
        }
        .space-y-13 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 26rpx;
          }
          .button_2 {
            padding: 24rpx 0;
            background-color: #ffffff;
            border-radius: 40rpx;
            box-shadow: 0px 6rpx 16rpx #00000029;
            width: 178rpx;
          }
          
          .section_5 {
            padding: 40rpx 58rpx;
            background-color: #e5e5e566;
            border-radius: 60rpx;
          }
          .group_4 {
            padding-bottom: 120rpx;
            width: 248rpx;
            // .section_3 {
            //   background-color: #4cb1e2;
            //   border-radius: 24rpx;
            //   width: 160rpx;
            //   height: 88rpx;
            // }
            // .pos_2 {
            //   position: absolute;
            //   left: 0;
            //   right: 0;
            //   top: 14rpx;
            // }
            // .pos_3 {
            //   position: absolute;
            //   left: 0;
            //   right: 0;
            //   top: 14rpx;
            // }
            .section_6 {
              background-color: #59a09e;
              border-radius: 24rpx;
              width: 160rpx;
              height: 88rpx;
            }
            .text-wrapper_3 {
              padding: 72rpx 0 84rpx;
              background-color: #81d9d3;
              border-radius: 24rpx;
              width: 248rpx;
              .text_8 {
                line-height: 36rpx;
              }
            }
            .pos_11 {
              position: absolute;
              left: 0;
              right: 0;
              top: 14rpx;
            }
            .pos_12 {
              position: absolute;
              left: 0;
              right: 0;
              top: 14rpx;
            }
          }
		  
		  .group_5 {
		    .section_6 {
		      background-color: #4cb1e2;
		      border-radius: 24rpx;
		      width: 160rpx;
		      height: 88rpx;
		    }
		    .text-wrapper_3 {
		      padding: 72rpx 0 84rpx;
		      background-color: #8ddaff;
		      border-radius: 24rpx;
		      width: 248rpx;
		      .text_8 {
		        line-height: 36rpx;
		      }
		    }
		  }
		  
		  
          .font_4 {
            font-size: 38rpx;
            font-family: SegoeUI-Bold;
            line-height: 35rpx;
            font-weight: 700;
            color: #ffffff;
          }
        }
        .font_2 {
          font-size: 32rpx;
          font-family: SegoeUI-Bold;
          line-height: 30rpx;
          font-weight: 700;
          color: #78708c;
        }
      }
      .space-y-19 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 38rpx;
        }
      }
    }
  }
//-----------------------------------------------------------------------------
.page2 {//预约page2
	position: fixed;
    background-color: #ffffff;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .group {
      padding: 36rpx 40rpx 30rpx;
      .space-y-24 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 30rpx;
        }
        .group_4 {
          padding: 0 10rpx;
          .space-x-20 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 40rpx;
            }
            .text_2 {
              line-height: 30rpx;
            }
            .text_3 {
              color: #b4b4b4;
            }
          }
          .text-wrapper {
            padding: 8rpx 0;
            background-color: #65cbc8;
            border-radius: 60rpx;
            width: 146rpx;
            height: 56rpx;
            .text_4 {
              color: #ffffff;
            }
          }
          .font_3 {
            font-size: 28rpx;
            font-family: SegoeUI-Bold;
            line-height: 40rpx;
            font-weight: 700;
          }
        }
        .space-y-14 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 28rpx;
          }
          .list-item {
            padding: 20rpx 24rpx;
            background-color: #edf2f7;
            border-radius: 40rpx;
            box-shadow: 0px 1rpx 6rpx #00000029;
            .section_2 {
              background-color: #ebebeb;
              border-radius: 40rpx;
              width: 170rpx;
              height: 170rpx;
			  overflow: hidden;
			  image{
				  width: 170rpx;
				  height: 170rpx;
			  }
            }
            .space-y-9 {
              & > view:not(:first-child),
              & > text:not(:first-child),
              & > image:not(:first-child) {
                margin-top: 18rpx;
              }
              .group_5 {
                margin-top: 20rpx;
                .font_5 {
                  font-size: 40rpx;
                  font-family: SegoeUI-Bold;
                  line-height: 37rpx;
                  font-weight: 700;
                  color: #202020;
                }
              }
              .space-x-8 {
                & > view:not(:first-child),
                & > text:not(:first-child),
                & > image:not(:first-child) {
                  margin-left: 16rpx;
                }
              }
              .text-wrapper_2 {
                margin-right: 12rpx;
                padding: 8rpx 0;
                background-color: #96a1f9;
                border-radius: 60rpx;
                width: 86rpx;
                height: 40rpx;
              }
              .space-x-12 {
                & > view:not(:first-child),
                & > text:not(:first-child),
                & > image:not(:first-child) {
                  margin-left: 24rpx;
                }
              }
              .font_6 {
                font-size: 24rpx;
                font-family: SegoeUI;
                line-height: 22rpx;
                color: #202020;
              }
              .group_6 {
                padding: 0 4rpx;
				.shizhong{
					height: 26rpx;
				}
                .section_3 {
                  background-color: #00000000;
                  width: 26rpx;
                  height: 26rpx;
                }
                .font_7 {
                  font-size: 24rpx;
                  font-family: SegoeUI;
                  line-height: 22rpx;
                  color: #000000;
                }
                .text_5 {
                  margin-left: 8rpx;
                  line-height: 23rpx;
                }
              }
            }
          }
          .space-x-14 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 28rpx;
            }
          }
        }
        .font_2 {
          font-size: 32rpx;
          font-family: SegoeUI-Bold;
          line-height: 29rpx;
          font-weight: 700;
          color: #202020;
        }
      }
    }
    .space-y-19 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 38rpx;
      }
    }
    .font_4 {
      font-size: 24rpx;
      font-family: SegoeUI-Bold;
      line-height: 22rpx;
      font-weight: 700;
      color: #ebebeb;
    }
  }

}
</style>


  
  