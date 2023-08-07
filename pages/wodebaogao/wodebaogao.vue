<template>
  <view class="flex-col page">

    <view class="flex-col flex-auto group">
      <view class="flex-col space-y-16">
        <text class="self-start font_1 text_2">数据分析</text>
		
        <view class="flex-col section">
			<view class="ct_tab flex-row justify-center group_2 space-x-20">
				<view class="ct_item" :class="{'ct_active' : 0 == tabCur}" @click="clickCtTab(0)">
					<text class="font_2">近五天</text>
				</view>
				<view class="ct_item" :class="{'ct_active2' : 1 == tabCur}" @click="clickCtTab(1)">
					<text class="font_2">AI分析</text>
				</view>
			
			</view>
<!-- 			<br> -->
			
			<!-- <view class="flex-row justify-center group_2 space-x-20" v-if="showTab">
				<view class="flex-col justify-start items-center text-wrapper" :class="{'ct_active' : 0 == tabCur}" @click="clickCtTab(0)">
					<text class="font_2 text_3">近五天</text>
				</view>
				<view class="flex-col justify-start items-center text-wrapper_2" :class="{'ct_active' : 1 == tabCur}" @click="clickCtTab(1)">
					<text class="font_2 text_4">近来日记</text>
				</view>
			</view> -->
			
			<!-- <view class="ct_tab">
				<view class="ct_item" :class="{'ct_active' : 0 == tabCur}" @click="clickCtTab(0)">
					<text>文章</text>
				</view>
				<view class="ct_item" :class="{'ct_active' : 1 == tabCur}" @click="clickCtTab(1)">
					<text>视频</text>
				</view>
			
			</view> -->
			
			<!-- <view v-if="tabCur===0"> -->
				<view v-if="tabCur===0" class="charts-box">
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
				<!-- </view> -->
				
			<view v-if="tabCur===1">
				<!-- <view class="jinqi">
					<text class=" texta">近期状况:</text>
					<text class="textb">较为稳定，无太大的情绪波动</text>
				</view>
				<view class="jianyi">
					<text class="textc">建议</text>
				</view> -->
				<view class="container">
				  <view class="sectiona1">
				    <view class="jiaonang">
						<text class="header1">近期状况</text>
					</view>
					<view class="zhuangtai">
						<!-- <text class="pinjia">心情状态：</text> -->	
						<view class="youyi">
							<text class="pinjia2" v-if="">{{zhuangTai}}</text>
						</view>
					</view>
				    <view class="content1">AI分析：{{ recentStatus }}</view>
				  </view>
				  <view class="sectiona2">
				    <view class="jiaonang2">
						<text class="header2">AI建议</text>
					</view>
				    <view class="content2">{{ suggestions }}</view>
				  </view>
				</view>
				
				</view>
          <!-- <view class="flex-row justify-center group_2 space-x-20">
            <view class="flex-col justify-start items-center text-wrapper">
              <text class="font_2 text_3">近5天</text>
            </view>
            <view class="flex-col justify-start items-center text-wrapper_2">
              <text class="font_2 text_4">近30天</text>
            </view>
          </view> -->
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
		  
		  <!-- <view class="charts-box">
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
		  </view> -->
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
			  <view class="weizhi1">
			  	<image class="tupiana" src="../../static/jiantou.png" mode=""></image>
			  </view>
			  
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
			  <view class="weizhi2">
			  	<image class="tupiana" src="../../static/jiantou.png" mode=""></image>
			  </view>
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
			  <view class="weizhi3">
			  	<image class="tupiana" src="../../static/jiantou.png" mode=""></image>
			  </view>
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
		  			  <view class="weizhi3">
		  			  	<image class="tupiana" src="../../static/jiantou.png" mode=""></image>
		  			  </view>
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
					<view class="weizhi3">
			  	<image class="tupiana" src="../../static/jiantou.png" mode=""></image>
			  </view>
					  
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
	let storedData = uni.getStorageSync('chartData');
      return {
		  zhuangTai:"平静",
		  recentStatus: "心情状态比较平稳，没有较大的起伏。",
		  suggestions: "培养积极思维，保持健康生活习惯，学会情绪管理，寻找支持和放松方式，设定合理目标和时间管理，以及进行自我关爱和照顾。",
			showTab: true,
		    tabCur:0,
    		cWidth: '',
    		cHeight: '',
		chartData: storedData ? JSON.parse(storedData) : {
        categories: ["高兴","乐观","平静","低迷","沮丧"],
        series: [
          {
            name: "情绪轨迹",
            linearColor: [
              [0, "#1890FF"],
              [0.25, "#00B5FF"],
              [0.5, "#00D1ED"],
              [0.75, "#00E6BB"],
              [1, "#90F489"]
            ],
            setShadow: [3, 8, 10, "#1890FF"],
            data: [75,75,90,75,75]
          },
        ]
      }, // 从本地存储中获取折线图的数据
        latestDates: [],
		showText: false,
		// chartData: uni.getStorageSync('chartData') || [],
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
		      showBox: false,
		      showArrow: false,
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
	// onLoad() {
	//     // 从本地存储中获取数据
	// 	this.chartData=JSON.parse(uni.getStorageSync('chartData'));
	//     // const storedData = uni.getStorageSync('chartData');
	//     // if (storedData) {
	//     // this.chartData = JSON.parse(storedData);
	//     // }
	//   },
	mounted() {
	  this.getLatestDates();
	  setTimeout(() => {
	      this.showText = true;
	    }, 200); // 延时1秒后显示文字
		
	// this.chartData = {
	// 	categories: ["高兴","乐观","平静","低迷","沮丧"],
	// 	series: [
	// 	  {
	// 	    name: "情绪轨迹",
	// 	      			linearColor: [
	// 	      			  [
	// 	      			    0,
	// 	      			    "#1890FF"
	// 	      			  ],
	// 	      			  [
	// 	      			    0.25,
	// 	      			    "#00B5FF"
	// 	      			  ],
	// 	      			  [
	// 	      			    0.5,
	// 	      			    "#00D1ED"
	// 	      			  ],
	// 	      			  [
	// 	      			    0.75,
	// 	      			    "#00E6BB"
	// 	      			  ],
	// 	      			  [
	// 	      			    1,
	// 	      			    "#90F489"
	// 	      			  ]
	// 	      			],
	// 	      			setShadow: [
	// 	      			  3,
	// 	      			  8,
	// 	      			  10,
	// 	      			  "#1890FF"
	// 	      			],
	// 	    data: [75,75,75,75,75]
	// 	  },
	// 	  // {
	// 	  //   name: "成交量B",
	// 	  //   data: [70,40,65,100,44]
	// 	  // },
	// 	  // {
	// 	  //   name: "成交量C",
	// 	  //   data: [100,80,95,150,112]
	// 	  // }
	// 	]
	// 	};
		
		const emoji = decodeURIComponent(this.$route.query.emoji);
		
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
		  this.zhuangTai="乐观";
		  this.recentStatus="心情状态良好，情绪曲线呈现一定的上升趋势。";
		  this.suggestions="保持积极心态，寻找乐趣和感恩之心。同时也要积极面对挑战，将注意力集中在积极的方面，并寻找解决问题的方法。"
		} else if (emoji === "../../static/bqb4.png") {
		  // 选择第三个图片，最右边的数据减10
		  this.chartData.series.forEach((series) => {
		    series.data[series.data.length - 1] += 35;
		  });
		  this.zhuangTai="高兴";
		  this.recentStatus="心情状态优秀，情绪曲线上升趋势明显。";
		  this.suggestions="继续保持积极乐观的心态，享受当下的快乐。同时，分享快乐，传递正能量。也可以尝试新的事物，挑战自己，扩展自己的兴趣爱好，让快乐不断延续。"
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
		  this.zhuangTai="低迷";
		  this.recentStatus="心情状态低落，情绪曲线有一定的下降趋势。";
		  this.suggestions="倾听内心，寻求支持。关注身体，调整思维。寻找乐趣，接受帮助。坚持与希望同行，你不孤单。相信自己，迎接新的开始。"
		} else if (emoji === "../../static/bqb7.png") {
		  // 选择第三个图片，最右边的数据减10
		  this.chartData.series.forEach((series) => {
		    series.data[series.data.length - 1] -= 30;
		  });
		  this.zhuangTai="沮丧";
		  this.recentStatus="心情状态消沉，情绪曲线下降趋势明显。";
		  this.suggestions="跟亲朋好友分享，寻求支持；找些让自己开心的活动，舒缓压力；加入支持性社交群体，获得情感支持；注重身体健康和情绪护理；如果需要，寻求专业帮助。"
		} else if (emoji === "../../static/bqb8.png") {
		  // 选择第三个图片，最右边的数据减10
		  this.chartData.series.forEach((series) => {
		    series.data[series.data.length - 1] += 30;
		  });
		  this.zhuangTai="高兴";
		  this.recentStatus="心情状态优秀，上升趋势明显。";
		  this.suggestions="继续保持积极乐观的心态，享受当下的快乐。同时，分享快乐，传递正能量。也可以尝试新的事物，挑战自己，扩展自己的兴趣爱好，让快乐不断延续。"
		}
		
		// 将更新后的数据保存到本地存储
		uni.setStorageSync('chartData', JSON.stringify(this.chartData));
		
		const lastData = this.chartData.series[this.chartData.series.length - 1];

		console.log(lastData);
		
    // 获取传递过来的图片路径参数
    // const emoji = decodeURIComponent(this.$route.query.emoji);

    // 根据选择的图片路径对折线图最右边的数据进行增减操作
 //    if (emoji === "../../static/bqb1.png") {
 //      // 选择第一个图片，最右边的数据加10
 //      const series = this.chartData.series.data;
 //      series.data[series.data.length - 1] += 10;
 //      this.chartData.series.data = series;
 //    } else if (emoji === "../../static/bqb2.png") {
 //      // 选择第二个图片，最右边的数据加20
 //      const series = this.chartData.series;
 //      series[series.length - 1] += 20;
 //      this.chartData.series.data = series;
 //    } else if (emoji === "../../static/bqb3.png") {
 //      // 选择第三个图片，最右边的数据减10
 //      const series = this.chartData.series;
 //      series[series.length - 1] -= 10;
 //      this.chartData.series.data = series;
 //    }
	// else if (emoji === "../../static/bqb4.png") {
	//   // 选择第三个图片，最右边的数据减10
	//   const series = this.chartData.series;
	//   series[series.length - 1] -= 10;
	//   this.chartData.series.data = series;
	// }
	// else if (emoji === "../../static/bqb5.png") {
	//   // 选择第三个图片，最右边的数据减10
	//   const series = this.chartData.series;
	//   series[series.length - 1] -= 10;
	//   this.chartData.series.data = series;
	// }
	// else if (emoji === "../../static/bqb6.png") {
	//   // 选择第三个图片，最右边的数据减10
	//   const series = this.chartData.series;
	//   series[series.length - 1] -= 10;
	//   this.chartData.series.data = series;
	// }
	// else if (emoji === "../../static/bqb7.png") {
	//   // 选择第三个图片，最右边的数据减10
	//   const series = this.chartData.series;
	//   series[series.length - 1] -= 10;
	//   this.chartData.series.data = series;
	// }
	// else if (emoji === "../../static/bqb8.png") {
	//   // 选择第三个图片，最右边的数据减10
 //      const series = this.chartData.series.data;
 //      series.data[series.data.length - 1] += 10;
 //      this.chartData.series.data = series;
	// }
	
	
	
	
	
	
		
	},
	
	computed: {
	  sortedDates() {
	    return this.latestDates.sort((a, b) => a - b);
	  }
	},
    methods: {
		clickCtTab(ctCur){
			this.tabCur  = ctCur
			// console.log(this.tabCur )
		},
		
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
          // this.chartData = JSON.parse(JSON.stringify(res));
        },500);
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
	.weizhi1{
		padding-left: 175rpx;
	}
	.weizhi2{
		padding-left: 170rpx;
	}
	.weizhi3{
		padding-left: 152rpx;
	}
	.tupiana{
		width: 30rpx;
		height: 30rpx;
	}
	.jiaonang2{
		text-align: center;
		width:150rpx;
		background-color: rgb(104,82,204 );
		border-radius: 10px;
		margin-bottom: 15rpx;
		
	}
	.jiaonang{
		padding-left: 5rpx;
		text-align: left;
		width:200rpx;
		// background-color: rgb(104,82,204 );
		border-radius: 10px;
		margin-top: 20rpx;
	}
.container {
  padding: 20px;
/*  background-color: #f2f2f2; */

}
.sectiona1 {
  margin-bottom: 11px;
  background-color:#fff;
  // background-color: rgba(109,203,200, 0.4);
   // background-color: rgb(245,246,250);
  // padding: 15px;
  border-radius: 15px;
  padding-left: 10rpx;
  
}
.sectiona2 {
	margin-top: 50rpx;
  margin-bottom: 11px;
  background-color:#f2f2f2;
  // background-color: rgba(109,203,200, 0.4);
   // background-color: rgb(245,246,250);
  padding: 15px;
  border-radius: 15px;
}
.header1 {
	font-family: SegoeUI;
  font-size: 18px;
  color: #666666;
  font-weight: bold;
}
.header2 {
	font-family: SegoeUI;
  font-size: 18px;
  color: #fff;
  font-weight: bold;
}
.zhuangtai{
	padding-bottom: 30rpx;
}
.pinjia{
	font-family: SegoeUI;
	font-size: 16px;
	color: #666666;
	line-height: 1.5;
	padding-left: 8rpx;
}
.pinjia2{
	color:#fff;
	font-size: 55rpx;
	font-weight: 700;
	justify-content: center;
	padding-left: 15rpx;
	
}
.youyi{
	float: right;
	margin-top: -50rpx;
	padding-right: 20rpx;
	padding-bottom: 0rpx;
	background: linear-gradient(135deg, rgb(104,82,204 ),#65cbc8);
	 // background: linear-gradient(45deg, rgba(148,210,243, 1), rgba(137,250,178, 1));
	 // background-color:rgb(104,82,204);
	 // background: linear-gradient(
	 //        to bottom right, 
	 //        #eafbff 40%,
	 //        #edfbff 80%,
	 //        #edfbfe 80%,
	 //        #e8f8fe 80%,
	 //        #eaf1fb 80%,
	 //        #e8e6fb 100%
	 //      );
	border-radius: 30rpx;
}
.content1 {
	font-family: SegoeUI;
  font-size: 15px;
  color: #666666;
  line-height: 1.5;
  padding-left: 8rpx;
  margin-top: -15rpx;
}	
.content2 {
	font-family: SegoeUI;
  font-size: 16px;
  color: #666666;
  line-height: 1.5;
  padding-left: 8rpx;
}	

	.jinqi{
		margin-top: 30rpx;
		margin-left: 20rpx;
		
	}
	.texta{
		  font-size: 38rpx;
		  font-family: SegoeUI;
		  line-height: 33rpx;
		  color: #787a8c;
		  line-height: 32rpx;
	}
	.textb{
		  font-family: SegoeUI;
		  color: #787a9c;
		  line-height: 32rpx;
	}
	.ct_item{
		//width: 20%;
		padding-bottom: 15rpx;
	}
	// .ct_item text{//小横杠字体距离
	// 	padding: 5rpx 0;
		
	// }
	.ct_active{
		color: #fff;//字体颜色
		background-color: #65cbc8;
		border-radius: 30rpx;
		width: 200rpx;
		text-align: center;
	}
	.ct_active2{
		color: #fff;//字体颜色
		background-color: #65cbc8;
		border-radius: 30rpx;
		width: 200rpx;
		text-align: center;
	}
	// .ct_active text{
	// 	//小横杠
	// 	border-bottom: 5px solid #65cbc8;
		
	// }
	.ct_tab{
		width: 100%;
		margin: 0 auto;
		padding: 15rpx 0;
		font-size: 45rpx;
		font-weight: bold;
		color: #666666;
		background-color: #fff;
		display: flex;
		justify-content: space-evenly;
		align-items: center;
	}
	
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
	  height: 300px;
	  margin-top: -40rpx;
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
	width: 100rpx;
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
          padding: 46rpx 10rpx 36rpx;
          background-color: #ffffff;
          box-shadow: 0px 6rpx 16rpx #a5a5a529;
          .group_2 {
            padding: 0 56rpx;
            .text-wrapper {
              padding: 16rpx 0;
              background-color: #65cbc8;
              border-radius: 40rpx;
              width: 220rpx;
              height: 66rpx;
              .text_3 {
                color: #000000;
              }
            }
            .text-wrapper_2 {
              padding: 16rpx 0;
              background-color: #edf2f7;
              border-radius: 40rpx;
              width: 220rpx;
              height: 66rpx;
              .text_4 {
                color: #000000;
              }
            }
            .font_2 {
              font-size: 40rpx;
              font-family: SegoeUI-Bold;
              line-height: 30rpx;
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
