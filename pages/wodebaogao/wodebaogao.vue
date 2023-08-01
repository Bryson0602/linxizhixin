<template>
  <view class="flex-col page">
    <view class="flex-col flex-auto group">
      <view class="flex-col space-y-16">
        <text class="self-start font_1 text_2">数据分析</text>
        <view class="flex-col section">
          <view class="flex-row justify-center group_2 space-x-20">
            <view class="flex-col justify-start items-center text-wrapper">
              <text class="font_2 text_3">近7天</text>
            </view>
            <view class="flex-col justify-start items-center text-wrapper_2">
              <text class="font_2 text_4">近30天</text>
            </view>
          </view>
          <!-- <view class="flex-row justify-around group_3">
            <view class="flex-row space-x-20">
              <view class="flex-col items-center space-y-50">
                <text class="font_3">高</text>
                <text class="font_3">中</text>
                <text class="font_3">低</text>
                <text class="font_3 text_5">无</text>
              </view>
              <view class="self-start section_3"></view>
            </view>
            <view class="self-start section_4"></view>
            <view class="self-start section_5"></view>
            <view class="self-center section_2"></view>
            <view class="self-start section_6"></view>
          </view>
          <!-- <view class="flex-row justify-between group_4">
            <text class="font_3">抑郁</text>
            <text class="font_3">焦虑</text>
            <text class="font_3">燥怒</text>
            <text class="font_3">不安</text>
            <text class="font_3">恐惧</text>
          </view>
          <view class="flex-row justify-center group_5 space-x-12">
            <view class="section_7"></view>
            <view class="section_8"></view>
            <view class="section_8"></view>
            <view class="section_8"></view>
          </view> -->
		  <view class="charts-box">
		    <qiun-data-charts 
		      type="line"
		      :opts="opts"
		      :chartData="chartData"
		    />
		  	<view class="date-container">
		  	  <view v-for="(date, index) in sortedDates" :key="index" class="date-item">
		  	    <transition name="fade">
		  	      <p v-if="showText">{{ formatDate(date) }}</p>
		  	    </transition>
		  	  </view>
		  	</view>
		  </view>
        </view>
		
		
      </view>
      <view class="flex-col group_6 space-y-12">
        <text class="self-start font_1 text_6">历史报告</text>
        <view class="flex-col">
          <view class="flex-col justify-start items-start section_9">
            <view class="flex-row items-center section_10 space-x-12">
              <image
                class="image_2"
                src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901700541890096354.png"
              />
              <view class="flex-col items-start space-y-8">
                <text class="font_4">SDS抑郁自评测试</text>
                <text class="font_5 text_7">2023.7.9</text>
              </view>
			  <img class="tupian2" src="../../static/jiantou.png" alt="">
            </view>
          </view>
          <view class="flex-col justify-start items-start relative section_9 view">
            <view class="flex-row items-center section_10 space-x-12">
              <image
                class="image_2"
                src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901700541912876113.png"
              />
              <view class="flex-col items-start space-y-12">
                <text class="font_4">心理卫生评定测试</text>
                <text class="font_5 text_7">2023.6.15</text>
              </view>
			  <img class="tupian3" src="../../static/jiantou.png" alt="">
            </view>
          </view>
		  <view class="flex-col justify-start items-start relative section_9 view">
		    <view class="flex-row items-center section_10 space-x-12">
		      <image
		        class="image_2"
		        src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901700541927764165.png"
		      />
		      <view class="flex-col items-start space-y-12">
		        <text class="font_4">MBTI人格测试分析</text>
		        <text class="font_5 text_7">2023.6.15</text>
		      </view>
			  <img class="tupian" src="../../static/jiantou.png" alt="">
		    </view>
		  </view>
		  <view class="flex-col justify-start items-start relative section_9 view">
		    <view class="flex-row items-center section_10 space-x-12">
		      <image
		        class="image_2"
		        src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901700541927764165.png"
		      />
		      <view class="flex-col items-start space-y-12">
		        <text class="font_4">MBTI人格测试分析</text>
		        <text class="font_5 text_7">2023.6.15</text>
		      </view>
		  			  <img class="tupian" src="../../static/jiantou.png" alt="">
		    </view>
		  </view>
		  <view class="flex-col justify-start items-start relative section_9 view">
		    <view class="flex-row items-center section_10 space-x-12">
		      <image
		        class="image_2"
		        src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901700541927764165.png"
		      />
		      <view class="flex-col items-start space-y-12">
		        <text class="font_4">MBTI人格测试分析</text>
		        <text class="font_5 text_7">2023.6.15</text>
		      </view>
		  			  <img class="tupian" src="../../static/jiantou.png" alt="">	
					  
		    </view>
		  </view>
          <!-- <view class="flex-col justify-start items-start relative group_7">
            <view class="relative section_11"></view>
            <view class="flex-row section_9 space-x-14 pos">
              <image
                class="image_2"
                src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901700541927764165.png"
              />
              <text class="self-start font_4 text_8">MBTI人格测试分析</text>
            </view>
          </view> -->
        </view>
      </view>
    </view>
  </view>
</template>

<script>
	// import uCharts from '@../../../uni_modules/qiun-data-charts/js_sdk/u-charts/u-charts.js'; //引入js文件
	// var _self; //用于全局使用this
	// var canvaLineA = null; //uCharts实例
  export default {
    components: {},
    data() {
      return {
    		cWidth: '',
    		cHeight: '',
        chartData: {},
        latestDates: [],
		showText: false,
        //您可以通过修改 config-ucharts.js 文件中下标为 ['line'] 的节点来配置全局默认参数，如都是默认参数，此处可以不传 opts 。实际应用过程中 opts 只需传入与全局默认参数中不一致的【某一个属性】即可实现同类型的图表显示不同的样式，达到页面简洁的需求。
		opts: {
		  timing: "easeOut",
		  duration: 500,
		  rotate: false,
		  rotateLock: false,
		  color: ["#1890FF","#91CB74","#FAC858","#EE6666","#73C0DE","#3CA272","#FC8452","#9A60B4","#ea7ccc"],
		  padding: [60,10,10,18],
		  fontSize: 13,
		  fontColor: "#666666",
		  dataLabel: false,
		  dataPointShape: false,
		  dataPointShapeType: "solid",
		  touchMoveLimit: 60,
		  enableScroll: false,
		  enableMarkLine: false,
		  legend: {
		    show: true,
		    position: "top",
		    float: "center",
		    padding: 5,
		    margin: 5,
		    backgroundColor: "rgba(0,0,0,0)",
		    borderColor: "rgba(0,0,0,0)",
		    borderWidth: 0,
		    fontSize: 13,
		    fontColor: "#666666",
		    lineHeight: 11,
		    hiddenColor: "#CECECE",
		    itemGap: 10
		  },
		  xAxis: {
		    disableGrid: true,
		    disabled: true,
		    axisLine: true,
		    axisLineColor: "#CCCCCC",
		    calibration: false,
		    fontColor: "#666666",
		    fontSize: 13,
		    lineHeight: 20,
		    marginTop: 4,
		    rotateLabel: false,
		    rotateAngle: 45,
		    itemCount: 5,
		    boundaryGap: "center",
		    splitNumber: 5,
		    gridColor: "#CCCCCC",
		    gridType: "solid",
		    dashLength: 8,
		    gridEval: 1,
		    scrollShow: false,
		    scrollAlign: "left",
		    scrollColor: "#A6A6A6",
		    scrollBackgroundColor: "#EFEBEF",
		    title: "",
		    titleFontSize: 13,
		    titleOffsetY: 0,
		    titleOffsetX: 0,
		    titleFontColor: "#666666",
		    format: ""
		  },
		  yAxis: {
		    gridType: "dash",
		    dashLength: 2,
		    disabled: false,
		    disableGrid: true,
		    splitNumber: 5,
		    gridColor: "#CCCCCC",
		    padding: 0,
		    showTitle: true,
		    data: [
		      {
		        type: "value",
		        position: "left",
		        disabled: true,
		        axisLine: true,
		        axisLineColor: "#CCCCCC",
		        calibration: false,
		        fontColor: "#666666",
		        fontSize: 13,
		        textAlign: "right",
		        title: "数值",
		        titleFontSize: 15,
		        titleOffsetY: -5,
		        titleOffsetX: 0,
		        titleFontColor: "#666666",
		        min: 0,
		        max: 150,
		        tofix: null,
		        unit: "",
		        format: ""
		      },
		      {
		        type: "categories",
		        position: "left",
		        disabled: false,
		        axisLine: true,
		        axisLineColor: "#CCCCCC",
		        calibration: false,
		        fontColor: "#666666",
		        fontSize: 13,
		        textAlign: "right",
		        title: "情绪",
		        titleFontSize: 15,
		        titleOffsetY: 0,
		        titleOffsetX: 0,
		        titleFontColor: "#666666",
		        min: 0,
		        max: 20,
		        tofix: null,
		        unit: "",
		        format: ""
		      }
		    ]
		  },
		  extra: {
		    line: {
		      type: "curve",
		      width: 10,
		      activeType: "hollow",
		      linearType: "custom",
		      onShadow: true,
		      animation: "vertical"
		    },
		    tooltip: {
		      showBox: true,
		      showArrow: true,
		      showCategory: false,
		      borderWidth: 0,
		      borderRadius: 5,
		      borderColor: "#000000",
		      borderOpacity: 0.7,
		      bgColor: "#6852CC",
		      bgOpacity: 0.7,
		      gridType: "solid",
		      dashLength: 4,
		      gridColor: "#CCCCCC",
		      boxPadding: 3,
		      fontSize: 13,
		      lineHeight: 20,
		      fontColor: "#FFFFFF",
		      legendShow: true,
		      legendShape: "auto",
		      splitLine: true,
		      horizentalLine: false,
		      xAxisLabel: false,
		      yAxisLabel: false,
		      labelBgColor: "#FFFFFF",
		      labelBgOpacity: 0.7,
		      labelFontColor: "#666666"
		    },
		    markLine: {
		      type: "solid",
		      dashLength: 4,
		      data: []
		    }
		  }
		}
    	  
      };
    },
	onReady() {
	  this.getServerData();
	},
	mounted() {
	  this.getLatestDates();
	  setTimeout(() => {
	      this.showText = true;
	    }, 500); // 延时1秒后显示文字
		
	this.chartData = {
		categories: ["高兴","乐观","平静","低迷","沮丧"],
		series: [
		  {
		    name: "情绪轨迹",
		      			linearColor: [
		      			  [
		      			    0,
		      			    "#1890FF"
		      			  ],
		      			  [
		      			    0.25,
		      			    "#00B5FF"
		      			  ],
		      			  [
		      			    0.5,
		      			    "#00D1ED"
		      			  ],
		      			  [
		      			    0.75,
		      			    "#00E6BB"
		      			  ],
		      			  [
		      			    1,
		      			    "#90F489"
		      			  ]
		      			],
		      			setShadow: [
		      			  3,
		      			  8,
		      			  10,
		      			  "#1890FF"
		      			],
		    data: [75,75,75,75,75]
		  },
		  // {
		  //   name: "成交量B",
		  //   data: [70,40,65,100,44]
		  // },
		  // {
		  //   name: "成交量C",
		  //   data: [100,80,95,150,112]
		  // }
		]
		};
		
		const emoji = decodeURIComponent(this.$route.query.emoji);
		console.log(emoji);
		
		if (emoji === "../../static/bqb1.png") {
		  // 选择第一个图片，最右边的数据加10
		  this.chartData.series.forEach((series) => {
		    series.data[series.data.length - 1] += 10;
		  });
		} else if (emoji === "../../static/bqb2.png") {
		  // 选择第二个图片，最右边的数据加20
		  this.chartData.series.forEach((series) => {
		    series.data[series.data.length - 1] += 5;
		  });
		} else if (emoji === "../../static/bqb3.png") {
		  // 选择第三个图片，最右边的数据减10
		  this.chartData.series.forEach((series) => {
		    series.data[series.data.length - 1] += 20;
		  });
		} else if (emoji === "../../static/bqb4.png") {
		  // 选择第三个图片，最右边的数据减10
		  this.chartData.series.forEach((series) => {
		    series.data[series.data.length - 1] += 35;
		  });
		} else if (emoji === "../../static/bqb5.png") {
		  // 选择第三个图片，最右边的数据减10
		  this.chartData.series.forEach((series) => {
		    series.data[series.data.length - 1] -= 10;
		  });
		} else if (emoji === "../../static/bqb6.png") {
		  // 选择第三个图片，最右边的数据减10
		  this.chartData.series.forEach((series) => {
		    series.data[series.data.length - 1] -= 25;
		  });
		} else if (emoji === "../../static/bqb7.png") {
		  // 选择第三个图片，最右边的数据减10
		  this.chartData.series.forEach((series) => {
		    series.data[series.data.length - 1] -= 35;
		  });
		} else if (emoji === "../../static/bqb8.png") {
		  // 选择第三个图片，最右边的数据减10
		  this.chartData.series.forEach((series) => {
		    series.data[series.data.length - 1] += 30;
		  });
		}
	},
	computed: {
	  sortedDates() {
	    return this.latestDates.sort((a, b) => a - b);
	  }
	},
    methods: {
      getServerData() {
        //模拟从服务器获取数据时的延时
        setTimeout(() => {
          //模拟服务器返回数据，如果数据格式和标准格式不同，需自行按下面的格式拼接
          let res = {
              // categories: ["高兴","乐观","平静","低迷","沮丧"],
              series: [
                {
         //          name: "情绪轨迹",
      			// linearColor: [
      			//   [
      			//     0,
      			//     "#1890FF"
      			//   ],
      			//   [
      			//     0.25,
      			//     "#00B5FF"
      			//   ],
      			//   [
      			//     0.5,
      			//     "#00D1ED"
      			//   ],
      			//   [
      			//     0.75,
      			//     "#00E6BB"
      			//   ],
      			//   [
      			//     1,
      			//     "#90F489"
      			//   ]
      			// ],
      			// setShadow: [
      			//   3,
      			//   8,
      			//   10,
      			//   "#1890FF"
      			// ],
         //          data: [75,75,75,75,75]
                },
                // {
                //   name: "成交量B",
                //   data: [70,40,65,100,44]
                // },
                // {
                //   name: "成交量C",
                //   data: [100,80,95,150,112]
                // }
              ]
            };
          this.chartData = JSON.parse(JSON.stringify(res));
        }, 500);
      },
      getLatestDates() {
        const currentDate = new Date();
        const latestDates = [];
        for (let i = 0; i < 5; i++) {
          const date = new Date(currentDate.getTime() - i * 24 * 60 * 60 * 1000);
          latestDates.push(date);
        }
        this.latestDates = latestDates;
      },
      formatDate(date) {
        const month = date.getMonth() + 1;
        const day = date.getDate();
        return `${month}-${day}`;
      }
    }
  };
</script>

<style scoped lang="scss">
	.fade-enter-active,
	.fade-leave-active {
	  transition: opacity 0.5s;
	}
	.fade-enter,
	.fade-leave-to {
	  opacity: 0;
	}
	.charts-box {
	  width: 600rpx;
	  height: 305px;
	  margin-top: -95rpx;
	  // position: relative;
	}
	.date-container {
	  display: flex;
	  flex-direction: row;
	  justify-content: space-between;
		margin-left: 81rpx;
		margin-top: -20rpx;
	}
	
	.date-item {
	  flex: 1;
	  text-align: center;
	  margin-right: -50rpx; /* 调整日期项之间的间距 */
	  color: #666666;
		font-size: 30rpx;
	}
	
	.date-item:last-child {
	  margin-right: 8rpx; /* 最后一个日期项的右间距设为0 */
	}
.tupian3{
	padding-left: 198rpx;
	width: 30rpx;
	height: 30rpx;
}
.tupian2{
	padding-left: 203rpx;
	width: 30rpx;
	height: 30rpx;
}
.tupian{
	padding-left: 180rpx;
	width: 30rpx;
	height: 30rpx;
}
.page {
	position: fixed;
    background-color: #f5f5f5;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .group {
      padding: 32rpx 40rpx 0;
      overflow-y: auto;
      .space-y-16 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 32rpx;
        }
        .text_2 {
          margin-left: 12rpx;
        }
        .section {
		border-radius: 30rpx;
          padding: 46rpx 0rpx 36rpx;
          background-color: #ffffff;
          box-shadow: 0px 6rpx 16rpx #a5a5a529;
          .group_2 {
            padding: 0 56rpx;
            .text-wrapper {
              padding: 16rpx 0;
              background-color: #65cbc8;
              border-radius: 40rpx;
              width: 230rpx;
              height: 66rpx;
              .text_3 {
                color: #ffffff;
              }
            }
            .text-wrapper_2 {
              padding: 16rpx 0;
              background-color: #edf2f7;
              border-radius: 40rpx;
              width: 230rpx;
              height: 66rpx;
              .text_4 {
                color: #b0b0b0;
              }
            }
            .font_2 {
              font-size: 40rpx;
              font-family: SegoeUI-Bold;
              line-height: 37rpx;
              font-weight: 700;
            }
          }
          .space-x-20 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 40rpx;
            }
            .space-y-50 {
              & > view:not(:first-child),
              & > text:not(:first-child),
              & > image:not(:first-child) {
                margin-top: 100rpx;
              }
              .text_5 {
                line-height: 31rpx;
              }
            }
            .section_3 {
              margin-top: 148rpx;
              background-color: #d8ebff;
              width: 50rpx;
              height: 268rpx;
            }
          }
          .group_3 {
            margin-top: 32rpx;
            .section_4 {
              margin-top: 280rpx;
              background-color: #d8ebff;
              width: 50rpx;
              height: 136rpx;
            }
            .section_5 {
              margin-top: 404rpx;
              background-color: #d8ebff;
              width: 50rpx;
              height: 10rpx;
            }
            .section_2 {
              background-color: #d8ebff;
              width: 50rpx;
              height: 398rpx;
            }
            .section_6 {
              margin-top: 404rpx;
              background-color: #d8ebff;
              width: 50rpx;
              height: 12rpx;
            }
          }
          .group_4 {
            margin-top: 16rpx;
            padding-left: 68rpx;
            padding-right: 20rpx;
          }
          .font_3 {
            font-size: 36rpx;
            font-family: SegoeUI-Bold;
            line-height: 33rpx;
            font-weight: 700;
            color: #b0b0b0;
          }
          .group_5 {
            margin-top: 44rpx;
            .section_7 {
              background-color: #65cbc8;
              border-radius: 50%;
              width: 22rpx;
              height: 22rpx;
            }
            .section_8 {
              background-color: #b0b0b0;
              border-radius: 50%;
              width: 22rpx;
              height: 22rpx;
            }
          }
        }
      }
      .group_6 {
        margin: 56rpx 0 -94rpx;
        .text_6 {
          margin-left: 12rpx;
          line-height: 45rpx;
        }
        .section_9 {
          background-color: #ffffff;
          border-radius: 24rpx;
          box-shadow: 0px 6rpx 16rpx #93939329;
          .section_10 {
            background-color: #ffffff;
            border-radius: 24rpx;
            box-shadow: 12rpx 6rpx 16rpx #93939329;
            width: 582rpx;
            .space-y-8 {
              & > view:not(:first-child),
              & > text:not(:first-child),
              & > image:not(:first-child) {
                margin-top: 16rpx;
              }
            }
            .font_5 {
              font-size: 44rpx;
              font-family: SegoeUI;
              line-height: 33rpx;
              color: #787a8c;
            }
            .text_7 {
              line-height: 32rpx;
            }
          }
          .image_2 {
            width: 36rpx;
            height: 170rpx;
          }
          .font_4 {
            font-size: 44rpx;
            font-family: SegoeUI;
            line-height: 41rpx;
            color: #787a8c;
          }
          .text_8 {
            margin-top: 48rpx;
          }
        }
        .view {
          margin-top: 36rpx;
        }
        .group_7 {
          padding-top: 36rpx;
          .section_11 {
            background-color: #ffffff;
            border-radius: 24rpx;
            box-shadow: 12rpx 6rpx 16rpx #93939329;
            width: 582rpx;
            height: 170rpx;
          }
          .space-x-14 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 28rpx;
            }
          }
          .pos {
            position: absolute;
            left: 0;
            right: 0;
            top: 36rpx;
          }
        }
      }
      .space-y-12 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 24rpx;
        }
      }
      .font_1 {
        font-size: 48rpx;
        font-family: SegoeUI-Bold;
        line-height: 44rpx;
        font-weight: 700;
        color: #202020;
      }
      .space-x-12 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 24rpx;
        }
      }
    }
  }
</style>
