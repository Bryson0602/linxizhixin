<template>
	<view class="flex-col page">
	  <view class="flex-col flex-auto group">
	    <view class="flex-col space-y-15">
	      <view class="flex-col section_2">
	        <view class="flex-col items-center space-y-6">
	          <text class="text_2">AI知识大挑战</text>
	         <!-- <text class="text_3">PHQ-9 Depression test</text> -->
	        </view>
	        <view class="flex-row items-center group_2 space-x-9">
	          <!-- <view class="section_3"></view> -->
	          <text class="font_2">请在十分钟内完成请在十分钟内完成请在十分钟内完成请在十分钟内完成请在十分钟内完成请在十分钟内完成请在十分钟内完成</text>
	        </view>
	        
	      </view>
	      <view class="flex-col justify-start items-start self-center section_4">
			  <view class="section_5" 
			  :style="{width: ((this.currentIdx + 1) / this.questionList.length * 100) + '%'}">
			  </view>
		  </view>
	    </view>
		
	    <view class="flex-row justify-between group_5">
	      <view class="flex-col justify-start items-center text-wrapper_2">
			  <text class="font_1 text_4">第{{currentIdx + 1}}题</text>
		  </view>
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
			<image class="tp" :src="item.dz" mode="aspectFit"></image>
			<view class="flex-row group_6 space-y-23">
			  <view class="flex-row space-y-23 ">
				<view class="box " 
				:class="option.selected ? 'selected' : ''"
				v-for="option in item.options"
				:key="option.id"
				@click="selectOption(option)" 
				>
					<view class="box flex-row justify-start items-start text-wrapper_3">
						<text class="font_3 text_7">{{option.name}}</text>
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
		  //诈病标记
		  number: 0,
		  //计时器
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
        {
            "_id": "64c4aa4efe975fba5ab12629",
            "id": 1,
            "isMultiple": false,
            "title": "自测入口界面，根据用户信息智能显示推荐的心理测试,使用的是NLP自然语言处理技术？",
			"dz":"../../static/gjxz.png",
            "options": [
                {
                    "id": 1,
                    "name": "√",
                    "label": "A",
                    "selected": false,
                    "score": 1
                },
                {
                    "id": 2,
                    "name": "×",
                    "label": "B",
                    "selected": false,
                    "score": 0
                }
            ],
            "posttime": 654321
        },
        {
            "_id": "64c4abe18b0da41af06b8371",
            "id": 2,
            "isMultiple": false,
            "title": "诈病检测功能中，AI是通过时间分析、逻辑分析、自然语言处理等技术来判断是否存在乱填的可能性？",
			"dz":"../../static/zbts.png",
            "options": [
                {
                    "id": 1,
                    "name": "√",
                    "label": "A",
                    "selected": false,
                    "score": 1
                },
                {
                    "id": 2,
                    "name": "×",
                    "label": "B",
                    "selected": false,
                    "score": 0
                }
            ],
            "posttime": 654320
        },
        {
            "_id": "64c4ac129755e344abedd648",
            "id": 3,
            "isMultiple": false,
            "title": "在结果页，AI仅仅是依靠得分来给出建议，并没有用到其他任何人工智能技术？",
			"dz":"../../static/jianyi.png",
            "options": [
                {
                    "id": 1,
                    "name": "√",
                    "label": "A",
                    "selected": false,
                    "score": 0
                },
                {
                    "id": 2,
                    "name": "×",
                    "label": "B",
                    "selected": false,
                    "score": 1
                }
            ],
            "posttime": 654319
        },
        {
            "_id": "64c4ac3555b3378257a78ca5",
            "id": 4,
            "isMultiple": false,
            "title": "MBTI测试开发过程中，可以使用机器学习算法对用户回答数据进行分析。通过训练模型，可以预测用户的人格类型?",
			"dz":"../../static/mbti.png",
            "options": [
                {
                    "id": 1,
                    "name": "√",
                    "label": "A",
                    "selected": false,
                    "score": 1
                },
                {
                    "id": 2,
                    "name": "×",
                    "label": "B",
                    "selected": false,
                    "score": 0
                }
            ],
            "posttime": 654318
        },
        {
            "_id": "64c4ac3555b3378257a78ca5",
            "id": 5,
            "isMultiple": false,
            "title": "AI通过对关键词与测试库的匹配程度进行评估，可以筛选出与用户关键词相关的心理测试?",
			"dz":"../../static/zc.png",
            "options": [
                {
                    "id": 1,
                    "name": "√",
                    "label": "A",
                    "selected": false,
                    "score": 1
                },
                {
                    "id": 2,
                    "name": "×",
                    "label": "B",
                    "selected": false,
                    "score": 0
                }
            ],
            "posttime": 654318
        }
    ],
	  };
    },

    methods: {
		//获取网络数据
		getData(){
			uni.request({
				url:"https://fc-mp-836eb6c6-0a4f-47c9-8149-6d32fa5245cd.next.bspapp.com/PHQ-9_get_All",
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
		  this.selectedOptions[this.currentIdx] = currentQuestion.options.filter(o => o.selected)
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
		   // 将上一题的选中选项赋值给selectedOptions数组
		       const prevQuestion = this.questionList[this.currentIdx]
		       if (prevQuestion) {
		         this.selectedOptions[this.currentIdx] = prevQuestion.options.filter(o => o.selected)
		       }
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
		  // 时间小于30s，判断诈病
		  const time = this.timer.split(':')
		  const minute = parseInt(time[0]) 
		  const second = parseInt(time[1])
		  console.log(minute);
	      console.log(second);
		  if(minute===0 && second<=10) {
		      this.number = 1
		  }
		  uni.redirectTo({
		  	url:"/pages/aizhishibg/aizhishibg?score=" + this.score + "&selectedOptions=" + JSON.stringify(this.selectedOptions)
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
	border-radius: 74rpx;
	cursor: pointer;
	user-select: none;
	transition: box-shadow 0.3s ease-in-out;
}
.selected {
  box-shadow: 0px 2px 5px 1px rgba(89, 133, 255, 1.0);
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
          background-image: linear-gradient(50deg, #05b0ff 0%, #d439ff 100%);
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
			  width: 100%;
            font-size: 24rpx;
            font-family: SegoeUI;
            line-height: 26rpx;
            color: #e7e7e7;
          }
          .group_4 {
            margin-top: 16rpx;
          }
        }
        .section_4 {
          background-color: #d8d8d8;
          border-radius: 24rpx;
          width: 408rpx;
          .section_5 {
            background-image: linear-gradient(50deg, #05b0ff 0%, #d467ff 100%);
            border-radius: 24rpx;
            width: 12%;
            height: 20rpx;
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
          background-color: #5fbdef;
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

        color: #3e3e3e;
        font-size: 40rpx;
        font-family: SegoeUI-Bold;
        font-weight: 700;
        line-height: 50rpx;
      }
      .group_6 {
		  
        margin-top: 10%;
        padding: 0 40rpx;
      }
	  .tp{
		  height: 400rpx;
		  //width: 230rpx;
		  margin-left: 40rpx;
	  }
      .space-y-23 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-left: 35%;
		  //background-color: #ffdad0;
        }
        .text-wrapper_3 {
          padding: 62rpx 92rpx;
          background-color: #dcdeff;
          border-radius: 74rpx;
          box-shadow: 0px 6rpx 12rpx #9b9b9b29;
		  
          .font_3 {
            font-size: 90rpx;
            font-family: SegoeUI-Bold;
            line-height: 37rpx;
            font-weight: 700;
            color: #4c7cff;
          }
          .text_7 {
            //margin-left: 52rpx;
          }
        }
      }
	  .bt{//三个按钮
		  margin-top: 70rpx;
		  margin-bottom: 150rpx;
		.button {
			//margin-top: 70rpx;
			padding: 32rpx 0 32rpx;
			background-color: #5fbdef;
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
			background-color: #5fbdef;
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