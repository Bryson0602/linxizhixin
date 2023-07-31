<template>
	<view class="flex-col page">
	  <view class="flex-col flex-auto group">
	    <view class="flex-col space-y-15">
	      <view class="flex-col section_2">
	        <view class="flex-col items-center space-y-6">
	          <text class="text_2">MBTI人格自测</text>
	          <text class="text_3">Myers-Briggs Type Indicator</text>
	        </view>
	        <view class="flex-row items-center group_2 space-x-9">
	          <view class="section_3"></view>
	          <text class="font_2">请在十分钟内完成</text>
	        </view>
	        <view class="flex-row items-center group_3 space-x-8">
	          <view class="section_3"></view>
	          <text class="font_2">诚实回答每个问题</text>
	        </view>
	        <view class="flex-row items-center group_4 space-x-8">
	          <view class="section_3"></view>
	          <text class="font_2">尽量不选择中立答案</text>
	        </view>
	      </view>
	      <view class="flex-col justify-start items-start self-center section_4">
			  <view class="section_5" 
			  :style="{width: ((this.currentIdx + 1) / this.allQuestions.length * 100) + '%'}">
			  </view>
		  </view>
	    </view>
		
	    <view class="flex-row justify-between group_5">
	      <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_1 text_4">{{currentIdx + 1}}</text></view>
	      <view class="flex-row section_6 space-x-10">
	        <image
	          class="shrink-0 self-center image"
	          src="https://codefun-proj-user-res-1256085488.cos.ap-guangzhou.myqcloud.com/649ac9cf5a7e3f0310c4dcea/64afb93ac430470012e44942/16901701522478464885.png"
	        />
	        <text class="self-start text_5">{{timer}}</text>
	      </view>
	    </view>
		
		<view 
		v-for="(item,index) in allQuestions"
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
		
			<button class="flex-col justify-start items-center self-center button" @click="next" :disabled="currentIdx === allQuestions.length - 1" v-show="currentIdx !== allQuestions.length - 1">
				<text class="text_8">下一题</text>
			</button>
			
			<button class="flex-col justify-start items-center self-center button2" @click="submit" v-show="currentIdx === allQuestions.length - 1">
				<text class="text_8">提 交</text>
			</button>
		</view>
	    
	  </view>
	</view>
</template>

<script>
export default {
  data() {
    return {
		// 合并题目数组
		allQuestions: [],

      timer: '00:00',
      currentIdx: 0,
      selectedOptions: [],
      questionList: [
        {
          id: 1,
          isMultiple: false,
          title: '你更倾向于在何种情况下获得能量？',
          answer: 'A',
          type: 'I',
          options: [
            { id: 1, name: '在独处时思考和反思', label: 'A', selected: false },
            { id: 2, name: '在社交场合中与他人互动', label: 'B', selected: false }
          ]
        },
        {
          id: 2,
          isMultiple: false,
          title: '你更倾向于如何获取信息？',
          answer: 'A',
          type: 'S',
          options: [
            { id: 1, name: '通过关注细节和具体事实', label: 'A', selected: false },
            { id: 2, name: '通过关注整体和抽象概念', label: 'B', selected: false }
          ]
        },
        {
          id: 3,
          isMultiple: false,
          title: '你更倾向于如何做决策？',
          answer: 'A',
          type: 'T',
          options: [
            { id: 1, name: '通过逻辑和客观分析', label: 'A', selected: false },
            { id: 2, name: '通过考虑他人的感受和价值观', label: 'B', selected: false }
          ]
        },
        {
          id: 4,
          isMultiple: false,
          title: '你更倾向于如何看待世界？',
          answer: 'A',
          type: 'J',
          options: [
            { id: 1, name: '喜欢计划和有结构的生活', label: 'A', selected: false },
            { id: 2, name: '喜欢灵活应对和开放的生活', label: 'B', selected: false }
          ]
        }
      ],
	  // 新增题目数组
	  additionalQuestions: [
		{
		  id: 5,
		  isMultiple: false,
		  title: '在处理冲突时，你更倾向于？',
		  options: [
			{ id: 1, name: '保持冷静和客观，寻求解决问题的最佳方案', label: 'A', selected: false },
			{ id: 2, name: '关注他人的感受和情绪，寻求和谐和共识', label: 'B', selected: false }
		  ]
		},
		{
		  id: 6,
		  isMultiple: false,
		  title: '在学习新事物时，你更倾向于？',
		  options: [
			{ id: 1, name: '喜欢通过实践和实际操作来学习', label: 'A', selected: false },
			{ id: 2, name: '喜欢通过阅读和理论来学习', label: 'B', selected: false }
		  ]
		},
		{
		  id: 7,
		  isMultiple: false,
		  title: '在工作中，你更倾向于？',
		  options: [
			{ id: 1, name: '独立工作，有自己的空间和时间', label: 'A', selected: false },
			{ id: 2, name: '与他人合作，共同完成任务', label: 'B', selected: false }
		  ]
		},
		{
		  id: 8,
		  isMultiple: false,
		  title: '当面临压力和挑战时，你更倾向于？',
		  options: [
			{ id: 1, name: '勇敢面对，寻求解决方案', label: 'A', selected: false },
			{ id: 2, name: '寻求支持和安慰，与他人分享感受', label: 'B', selected: false }
		  ]
		},
		{
		  id: 9,
		  isMultiple: false,
		  title: '在现实中，你更倾向于？',
		  options: [
			{ id: 1, name: '注重实际和现实情况', label: 'A', selected: false },
			{ id: 2, name: '喜欢探索新的可能性和想象力', label: 'B', selected: false }
		  ]
		},
		{
		  id: 10,
		  isMultiple: false,
		  title: '在组织活动时，你更倾向于？',
		  options: [
			{ id: 1, name: '喜欢提前安排并遵循计划', label: 'A', selected: false },
			{ id: 2, name: '更喜欢灵活调整和随机应变', label: 'B', selected: false }
		  ]
		},
		{
		  id: 11,
		  isMultiple: false,
		  title: '在与他人交往时，你更倾向于？',
		  options: [
			{ id: 1, name: '喜欢直接表达自己的观点和感受', label: 'A', selected: false },
			{ id: 2, name: '更倾向于倾听他人并保持和谐', label: 'B', selected: false }
		  ]
		},
		{
		  id: 12,
		  isMultiple: false,
		  title: '在学习中，你更倾向于？',
		  options: [
			{ id: 1, name: '喜欢专注于一项任务直到完成', label: 'A', selected: false },
			{ id: 2, name: '可以同时处理多个任务并灵活切换', label: 'B', selected: false }
		  ]
		},
		// 可以继续添加更多的题目
	  ]
    };
  },
//   computed: {
//   // 进度条的计算属性
//   progress() {
//     return ((this.currentIdx + 1) / this.allQuestions.length) * 100;
//   }
// }
// ,
created() {
  this.allQuestions = this.questionList.concat(this.additionalQuestions);
},
  methods: {
    selectOption(option) {
      const currentQuestion = this.allQuestions[this.currentIdx];
      if (!currentQuestion.isMultiple) {
        currentQuestion.options.forEach(o => {
          o.selected = false;
        });
      }
      option.selected = !option.selected;
    },
    prev() {
      if (this.currentIdx > 0) {
        this.currentIdx--;
      }
    },
    next() {
      if (this.currentIdx < this.allQuestions.length - 1) {
        this.currentIdx++;
      }
    },
    submit() {
      const answeredList = this.allQuestions.filter(q => {
        return q.options.some(option => option.selected);
      });
      if (answeredList.length < this.allQuestions.length) {
        uni.showModal({
          title: '温馨提示',
          content: '还有题目未作答',
          showCancel: false
        });
        return;
      }
      let result = '';
      this.questionList.forEach(question => {
        const selectedOption = question.options.find(option => option.selected);
        result += selectedOption.label;
      });
      // 根据选项生成MBTI人格类型
      const personalityType = this.generatePersonalityType(result);
      // uni.navigateTo({
      //   url: '/pages/ceshibaogao3/ceshibaogao3?type=' + personalityType
      // });
    },
    generatePersonalityType(result) {
      // 根据选项生成MBTI人格类型
      let personalityType = '';
      switch (result) {
        case 'AAAA':
          personalityType = 'ISTJ';
          break;
        case 'AAAB':
          personalityType = 'ISTP';
          break;
		case 'AABA':
		  personalityType = 'ISFJ';
		  break;
		case 'AABB':
		  personalityType = 'ISFP';
		  break;
		case 'ABAA':
		  personalityType = 'INTJ';
		  break;
		case 'ABAB':
		  personalityType = 'INTP';
		  break;
        case 'ABBA':
          personalityType = 'INFJ';
          break;
        case 'ABBB':
          personalityType = 'INFP';
          break;
		case 'BAAA':
		  personalityType = 'ESTJ';
		  break;
		case 'BAAB':
		  personalityType = 'ESTP';
		  break;
		case 'BABA':
		  personalityType = 'ESFJ';
		  break;
		case 'BABB':
		  personalityType = 'ESFP';
		  break;
        case 'BBAA':
          personalityType = 'ENTJ';
          break;
        case 'BBAB':
          personalityType = 'ENTP';
          break;
		case 'BBBA':
		  personalityType = 'ENFJ';
		  break;
		case 'BBBB':
		  personalityType = 'ENFP';
		  break;
					
        // 其他情况根据需要继续添加
        default:
          personalityType = 'Unknown';
          break;
      }
      //return personalityType;
	  console.log(personalityType);
	  uni.navigateTo({
	    url: '/pages/ceshibaogao3/ceshibaogao3?type=' + personalityType
	  });
	  // uni.showToast({
	  //   title: personalityType,
	  //   icon: 'none'  
	  // })
    },
	
    startTimer() {
      let minute = 0;
      let second = 0;
      setInterval(() => {
        second++;
        if (second >= 60) {
          minute++;
          second = 0;
        }
        this.timer = this.formatNumber(minute) + ':' + this.formatNumber(second);
      }, 1000);
    },
    formatNumber(num) {
      return num >= 10 ? num : '0' + num;
    }
  },
  onLoad() {
    this.startTimer();
  },
  onUnload() {
    clearInterval(this.timer);
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
  box-shadow: 0px 2px 5px 1px rgba(100, 83, 206, 0.8);
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
          background-color: #6453ce;
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
            line-height: 22rpx;
            color: #d8d8d8;
          }
          .group_4 {
            margin-top: 16rpx;
          }
        }
        .section_4 {
          background-color: #d8d8d8;
          border-radius: 24rpx;
          width: 608rpx;
          .section_5 {
            background-color: #6453ce;
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
          background-color: #6453ce;
          border-radius: 50%;
          width: 72rpx;
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
            line-height: 50rpx;
            font-weight: 700;
            color: #202020;
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
			background-color: #6453ce;
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
			background-color: #6453ce;
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