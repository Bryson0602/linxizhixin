<template>
	<view class="flex-col page">
	  <view class="flex-col flex-auto group">
	    <view class="flex-col space-y-15">
	      <view class="flex-col section_2">
	        <view class="flex-col items-center space-y-6">
	          <text class="text_2">机器学习技术</text>
	        </view>
	        <view class="flex-row items-center group_2 space-x-9">
	          <!-- <view class="section_3"></view> -->
	          <text class="font_2">机器学习（Machine Learning）是一种人工智能的分支领域，它通过使用统计学和算法来使计算机系统具备自主学习和改进的能力，从而实现对数据的分析、模式识别和预测。</text>
	        </view>
	        <view class="flex-row items-center group_3 space-x-8">
	          <!-- <view class="section_3"></view> -->
	          <!-- <text class="font_2">诚实回答每个问题</text> -->
	        </view>
	        <view class="flex-row items-center group_4 space-x-8">
	          <!-- <view class="section_3"></view> -->
	          <!-- <text class="font_2">尽量不选择中立答案</text> -->
	        </view>
	      </view>
	      <view class="flex-col justify-start items-start self-center section_4">
			  <view class="section_5" 
			  :style="{width: ((this.currentIdx + 1) / this.questionList.length * 100) + '%'}">
			  </view>
		  </view>
	    </view>
		
	    <view class="flex-row justify-between group_5">
	      <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_1 text_4">第{{currentIdx + 1}}题</text></view>
	      <!-- <view class="flex-row section_6 space-x-10">
	        <image
	          class="shrink-0 self-center image"
	          src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901701522478464885.png"
	        />
	        <text class="self-start text_5">{{timer}}</text>
	      </view> -->
	    </view>
		
		<view 
		v-for="(item,index) in questionList"
		:key="index"
		v-show="currentIdx === index"
		>
		
			<text class="self-center flex-row text_6">{{item.title}}</text>
			
			<view class="flex-col group_6 space-y-23">
			  <view class="flex-col space-y-23 ">
				<view class="box " 
				:class="option.selected ? 'selected' : ''"
				v-for="option in item.options"
				:key="option.id"
				@click="selectOption(option)" 
				>
					<view class="box flex-col justify-start items-start text-wrapper_3">
						<text class="font_3 text_7">{{option.label}}. {{option.name}}</text>
					</view>
				</view>
			  </view>
			</view>
		</view>
		<view class="flex-row bt">
			<button class="flex-col justify-start items-center self-center button1" @click="prev" :disabled="currentIdx === 0">
			<image src="../../static/zuojiantou.png" mode=""></image>
			</button>
		
			<button class="flex-col justify-start items-center self-center button" @click="next" :disabled="currentIdx === questionList.length - 1" v-show="currentIdx !== questionList.length - 1">
				<text class="text_8">下一题</text>
			</button>
			
			<button class="flex-col justify-start items-center self-center button2" @click="submit" v-show="currentIdx === questionList.length - 1">
				<text class="text_8">提 交</text>
			</button>
		</view>
	    
	  </view>
	</view>
</template>

<script>
  export default {
    components: {},
    data() {
      return {
		  timer: '00:00',
		  // 当前题目索引
		  currentIdx: 0, 
		  // 已获得的分数
		  score: 0,
		  // 选中的选项
		  selectedOptions: [],
		  // 是否显示答案 
		  showAnswer: false,
		  // 是否可以显示答案
		  canShowAnswer: false,
		  // 题目列表
		  questionList: [
		    // 题目1
		    {
		      id: 1,
		      isMultiple: false, // 是否多选
		      title: '监督学习中，训练数据应包括哪些部分？',
		      //answer: 'A', // 答案
		      //score: 2, // 分值
		      options: [ // 选项列表
		        {id: 1, name:'输入特征和输出变量', label: 'A', selected: false ,score: 1},
		        {id: 2, name:'输出变量和模型参数', label: 'B', selected: false ,score: 0}, 
		        {id: 3, name:'输入特征和模型参数', label: 'C', selected: false ,score: 0}
		      ]
		    },
		    {
		      id: 2,
		      isMultiple: false,
		      title: '深度学习涉及什么？',
		      //answer: 'C',
		      //score: 2,
		      options: [
		    	{id: 1, name:'模拟人类学习过程的机器学习算法', label: 'A', selected: false ,score: 0},
		    	{id: 2, name:'通过训练大量数据提高性能的神经网络技术', label: 'B', selected: false ,score: 1},
		    	{id: 3, name:'通过集成多个模型提高性能的机器学习技术', label: 'C', selected: false ,score: 0}
		      ]
		    },
		    {
		      id: 3,  
		      isMultiple: false,
		      title: '什么是梯度下降？',
		      //answer: 'B',
		      //score: 2,
		      options: [
		    	{id: 1, name:'一种优化算法，用于更新模型参数以最小化损失函数', label: 'A', selected: false ,score: 1},
		    	{id: 2, name:'一种特征选择算法，用于减少数据维度', label: 'B', selected: false ,score: 0},
		    	{id: 3, name:'一种评估模型性能的统计指标', label: 'C', selected: false ,score: 0}
		      ]
		    },
		    {
		      id: 4,
		      isMultiple: false,
		      title: '什么是正则化（Regularization）?',
		      //answer: 'C',
		      //score: 2,
		      options: [
		    	{id: 1, name:'一种特征选择算法，用于减少数据维度', label: 'A', selected: false ,score: 0},
		    	{id: 2, name:'一种评估模型性能的统计指标', label: 'B', selected: false ,score: 0},
		    	{id: 3, name:'一种用于控制模型复杂度的技术', label: 'C', selected: false ,score: 1},
				// {id: 4, name:'是的', label: 'D', selected: false ,score: 1},
		      ]
		    },
		    {
		      id: 5,
		      isMultiple: false,
		      title: '在监督学习中，什么是回归问题（Regression）？',
		      //answer: 'C',
		      //score: 2,
		      options: [
		    	{id: 1, name:'预测离散的类别或标签', label: 'A', selected: false ,score: 0},
		    	{id: 2, name:'预测连续的数值', label: 'B', selected: false ,score: 1},
		    	{id: 3, name:'对数据进行分类', label: 'C', selected: false ,score: 0},
				// {id: 4, name:'是的', label: 'D', selected: false},
		      ]
		    },
		    {
		      id: 6,
		      isMultiple: false,
		      title: '以下哪个算法适用于处理文本数据?',
		      //answer: 'C',
		      //score: 2,
		      options: [
		    	{id: 1, name:'支持向量机（SVM）', label: 'A', selected: false ,score: 1},
		    	{id: 2, name:'K均值聚类', label: 'B', selected: false ,score: 0},
		    	{id: 3, name:'主成分分析', label: 'C', selected: false ,score: 0},
				// {id: 4, name:'是的', label: 'D', selected: false},
		      ]
		    },
		    {
		      id: 7,
		      isMultiple: false,
		      title: '以下哪个算法常用于异常检测？',
		      //answer: 'C',
		      //score: 2,
		      options: [
		    	{id: 1, name:'支持向量机（SVM）', label: 'A', selected: false ,score: 1},
		    	{id: 2, name:'决策树', label: 'B', selected: false ,score: 0},
		    	{id: 3, name:'K均值聚类', label: 'C', selected: false ,score: 0},
				// {id: 4, name:'是的', label: 'D', selected: false},
		      ]
		    }
		  ],
	  };
    },

    methods: {
		//获取网络数据
		getData(){
			uni.request({
				url:"https://fc-mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.next.bspapp.com/GAD-7_get_All",
				success:res=>{
					console.log(res);
					//this.questionList=res.data.data
				}
			})
		},
		// 选择选项的方法
		selectOption(option) {
		  // 当前题目
		  const currentQuestion = this.questionList[this.currentIdx]
		  // 如果不是多选题,则先清空已选选项
		  if (!currentQuestion.isMultiple) {
		    currentQuestion.options.forEach(o => {
		      o.selected = false
		    })
		  }
		  // 切换选中状态
		  option.selected = !option.selected
		  // 检查答案
		  this.checkAnswer()
		},
		// 检查答案的方法
		checkAnswer() {
			const currentQuestion = this.questionList[this.currentIdx]
			const selectedOptions = currentQuestion.options.filter(o => o.selected)
			  
			let score = 0
			selectedOptions.forEach(option => {
			    score += option.score
			})
			
			this.score += score
		  // // 当前题目  
		  // const currentQuestion = this.questionList[this.currentIdx]
		  // // 获得所有选中的选项标签
		  // let selectedLabels = currentQuestion.options
		  //   .filter(option => option.selected)
		  //   .map(option => option.label)
		  // // 拼接为字符串,与答案比较  
		  // selectedLabels = selectedLabels.join('')
		  
		  // if (selectedLabels === currentQuestion.answer) {
		  //   // 如果符合答案,得分
		  //   currentQuestion.isCorrect = true
		  //   this.score += currentQuestion.score   
		  // } else {
		  //   currentQuestion.isCorrect = false
		  // }
		},
		// 上一题方法
		prev() {
		  if (this.currentIdx > 0) {
		    this.currentIdx--
		  } 
		},
		// 下一题方法
		next() {
		 if (this.currentIdx < this.questionList.length - 1) {
		   this.currentIdx++   
		 }
		},
		// 提交方法
		submit() {
		  // 检查是否全部作答
		  const answeredList = this.questionList.filter(q => {
		    return q.options.some(option => option.selected)   
		  })
		  if (answeredList.length < this.questionList.length) {
		    // 如果有未作答的,提示
		    // uni.showToast({
		    //   title: '还有题目未作答',
		    //   icon: 'none'
		    // })
			uni.showModal({
				title: '温馨提示',
				content: '还有题目未作答',
				showCancel: false
			});
		    return
		  }
		  // 显示得分
		  // uni.showToast({
		  //   title: `获得${this.score}分`,
		  //   icon: 'none'  
		  // })
		  console.log(this.score)
		  // 允许显示答案
		  this.canShowAnswer = true
		  uni.redirectTo({
		  	url:"/pages/jqxxbg/jqxxbg?score=" + this.score
		  })
		},

		// addShadow() {
		//   this.$refs.box.classList.add('active');
		// },
		// removeShadow() {
		//   this.$refs.box.classList.remove('active');
		// }
		bianse(){
			document.getElementById('box').style.background='red'
		},
		startTimer() {//计时器的方法
		  let minute = 0;
		  let second = 0;
		  setInterval(() => {
			second++;
			if(second >= 60) {
			  minute++;
			  second = 0;
			}
			this.timer = this.formatNumber(minute) + ':' + this.formatNumber(second);
		  }, 1000);
		},
		formatNumber(num) {//计时器的方法
		  return num >= 10 ? num : '0' + num;
		}
	},
	onLoad() {
		this.getData();
		this.startTimer();//加载计时器
	},
	onUnload() {
	  clearInterval(this.timer)//清除计时器
	}
  };
</script>

<style scoped lang="scss">
.box {
	border-radius: 24rpx;
	cursor: pointer;
	user-select: none;
	transition: box-shadow 0.3s ease-in-out;
}
.selected {
  box-shadow: 0px 2px 5px 1px #ff8769;
}

  .page {
	position: fixed;
    background-color: #f5f5f5;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .group {
      padding-bottom: 58rpx;
      overflow-y: auto;
      .space-y-15 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 30rpx;
        }
        .section_2 {
          padding: 60rpx 68rpx 60rpx 74rpx;
          background-image: linear-gradient(50deg, #ff8769 0%, #ffaa82 100%);
          box-shadow: 0px 6rpx 16rpx #a5a5a529;
          .space-y-6 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-top: 12rpx;
            }
            .text_2 {
              color: #ffffff;
              font-size: 56rpx;
              font-family: SegoeUI-Bold;
              font-weight: 700;
              line-height: 52rpx;
            }
            .text_3 {
              color: #ffffff;
              font-size: 34rpx;
              font-family: SegoeUI;
              line-height: 33rpx;
            }
          }
          .group_2 {
            margin-top: 40rpx;
          }
          .space-x-9 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 18rpx;
            }
          }
          .group_3 {
            margin-top: 16rpx;
          }
          .space-x-8 {
            & > view:not(:first-child),
            & > text:not(:first-child),
            & > image:not(:first-child) {
              margin-left: 16rpx;
            }
          }
          .section_3 {
            background-color: #d8d8d8;
            border-radius: 50%;
            width: 12rpx;
            height: 12rpx;
          }
          .font_2 {
            font-size: 24rpx;
            font-family: SegoeUI;
            line-height: 26rpx;
			width: 100%;
            color: #f7f7f7;
          }
          .group_4 {
            margin-top: 16rpx;
          }
        }
        .section_4 {
          background-color: #d8d8d8;
          border-radius: 24rpx;
          width: 508rpx;
          .section_5 {
            background-color: #ff8769;
            border-radius: 24rpx;
            width: 12%;
            height: 16rpx;
			transition: width 0.5s ease;
          }
        }
      }
      .group_5 {
        margin-top: 58rpx;
		margin-bottom: 58rpx;
        padding: 0 56rpx;
        .text-wrapper_2 {
          padding: 20rpx 0 16rpx;
          background-color: #ff8769;
          border-radius: 30rpx;
          width: 172rpx;
          height: 72rpx;
          .font_1 {
            font-size: 48rpx;
            font-family: SegoeUI-Bold;
            font-weight: 700;
          }
          .text_4 {
            color: #ffffff;
            line-height: 34rpx;
          }
        }
        .section_6 {
          padding: 10rpx 24rpx;
          background-color: #ffffff;
          border-radius: 32rpx;
          box-shadow: 0px 6rpx 16rpx #a5a5a529;
          height: 68rpx;
          .image {
            width: 48rpx;
            height: 48rpx;
          }
          .text_5 {
            margin-top: 13rpx;
            color: #707070;
            font-size: 36rpx;
            font-family: SegoeUI-Bold;
            font-weight: 700;
            line-height: 26rpx;
          }
        }
        .space-x-10 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-left: 20rpx;
          }
        }
      }
      .text_6 {
        margin:0 48rpx;

        color: #202020;
        font-size: 44rpx;
        font-family: SegoeUI-Bold;
        font-weight: 700;
        line-height: 50rpx;
      }
      .group_6 {
        margin-top: 108rpx;
        padding: 0 40rpx;
      }
      .space-y-23 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 46rpx;
        }
        .text-wrapper_3 {
          padding: 32rpx 0;
          background-color: #ffffff;
          border-radius: 24rpx;
          box-shadow: 0px 6rpx 12rpx #9b9b9b29;
          .font_3 {
            font-size: 40rpx;
            font-family: SegoeUI-Bold;
            line-height: 43rpx;
            font-weight: 700;
            color: #383838;
          }
          .text_7 {
            margin-left: 52rpx;
			margin-right: 20rpx;
          }
        }
      }
	  .bt{//三个按钮
		  margin-top: 70rpx;
		  margin-bottom: 150rpx;
		.button {
			//margin-top: 70rpx;
			padding: 32rpx 0 32rpx;
			background-color: #ff8769;
			border-radius: 32rpx;
			box-shadow: 0px 6rpx 16rpx #a5a5a529;
			width: 336rpx;
			.text_8 {
			  color: #ffffff;
			  font-size: 52rpx;
			  font-family: SegoeUI-Bold;
			  font-weight: 700;
			  line-height: 47rpx;
			}
		}
		  .button1 {
			//margin-top: 70rpx;
			//padding: 32rpx 0 32rpx;
			background-color: #ff8769;
			border-radius: 100rpx;
			box-shadow: 0px 6rpx 16rpx #a5a5a529;
			width: 100rpx;
			height: 100rpx;
			image{
				margin: auto 5rpx;
				width: 55rpx;
				height: 55rpx;
			}
		}
		  .button2 {
			//margin-top: 70rpx;
			padding: 32rpx 0 32rpx;
			background-color: #4ca178;
			border-radius: 32rpx;
			box-shadow: 0px 6rpx 16rpx #a5a5a529;
			width: 336rpx;
			.text_8 {
			  color: #ffffff;
			  font-size: 52rpx;
			  font-family: SegoeUI-Bold;
			  font-weight: 700;
			  line-height: 47rpx;
			}
		}
		  button[disabled]{
			background-color: #ccc;
		}
	  }
    }
  }
</style>