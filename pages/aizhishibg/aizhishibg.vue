<template>
  <view class="flex-col page space-y-16">
    <view class="flex-col relative">
      <view class="flex-col justify-start items-center self-start text-wrapper">
        <text class="font_1 text">AI知识大挑战</text>
      </view>
      <text class="self-end text_3">/5道</text>
      <view class="flex-row items-baseline button group space-x-20">
        <text class="flex-auto font_1 text_4">此次测验，您一共答对了：</text>
        <text class="shrink-0 text_2">{{this.score}}</text>
      </view>
    </view>
    <view class="flex-col">
      <view class="flex-row items-center section space-x-14">
        <image
          class="shrink-0 image"
          src="../../static/bqb41.png"
        />
        <text class="flex-auto text_5">做的不错！AI知识需要靠每日积累，灵犀知心带你探索更多AI知识</text>
      </view>
      <view class="flex-col list space-y-13">
        <view class="flex-col list-item space-y-14" v-for="(item, index) in items" :key="index">
          <view class="flex-row justify-between items-center">
            <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_2">第{{item.id}}题</text></view>
            <view class="group_2 view">
              <text class="font_3 text_6">正确答案：</text>
              <text :class="['font_4', item.name === '√' ? 'text-correct-green' : 'text-correct-red']">{{item.name}}</text>
              <text class="font_3">，你的答案</text>
              <text :class="['font_4', item.name1 === '√' ? 'text-correct-green' : 'text-correct-red']">{{item.name1}}</text>
            </view>
          </view>
          <view class="flex-col space-y-10">
            <text class="font_5">{{item.title}}</text>
            <view class="flex-col justify-start section_2">
              <view class="group_3">
                <text class="font_7 text_8">解析：</text>
                <text class="font_6">
                  {{item.jx}}
                </text>
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
    components: {},
    props: {},
    data() {
      return {
		score: 0,  
		selectedOptions: [], // 初始化 selectedOptions 数组
        items: [
			{
			    "_id": "64c4aa4efe975fba5ab12629",
			    "id": 1,
			    "isMultiple": false,
			    "title": "自测入口界面，根据用户信息智能显示推荐的心理测试,使用的是NLP自然语言处理技术？",
				"jx":"根据题目描述的情况，使用NLP自然语言处理技术可以实现智能显示推荐的心理测试。NLP可以对用户输入的文本进行词法分析、语义理解等处理，从中提取关键信息。从而智能显示推荐的心理测试。",
				"dz":"../../static/zbts.png",
				"name": "√",
				"name1": "√",
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
			            "score": 1
			        }
			    ],
			    "posttime": 654321
			},
			{
			    "_id": "64c4abe18b0da41af06b8371",
			    "id": 2,
			    "isMultiple": false,
			    "title": "诈病检测功能中，AI是通过时间分析、逻辑分析、自然语言处理等技术来判断是否存在乱填的可能性？",
				"jx":"在诈病检测功能中，AI可以利用多种技术来判断是否存在乱填，其中包括时间分析、逻辑分析和自然语言处理等技术。这些技术可以帮助AI更准确地识别潜在的虚假填写行为，提高效果和可靠性。",
				"dz":"../../static/bqb1.png",
				"name": "√",
				"name1": "×",
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
			    "posttime": 654320
			},
			{
			    "_id": "64c4ac129755e344abedd648",
			    "id": 3,
			    "isMultiple": false,
			    "title": "在结果页，AI仅仅是依靠得分来给出建议，并没有用到其他任何人工智能技术？",
				"jx":"除了依靠得分以外，AI在结果页还可以利用数据挖掘和机器学习、自然语言处理以及知识图谱和专家系统等技术，为用户提供更全面和准确的解释和建议。",
				"dz":"../../static/bqb2.png",
				"name": "×",
				"name1": "×",
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
				"jx":"在MBTI测试开发过程中，可以利用机器学习算法对用户回答数据进行分析，以及提供有关人格特征的解释和建议。但是，为了得到精确的测试结果，仍需要用户参与正式的MBTI测试过程。",
				"dz":"../../static/bqb3.png",
				"name": "√",
				"name1": "√",
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
			    "posttime": 654318
			},
			{
			    "_id": "64c4ac3555b3378257a78ca5",
			    "id": 5,
			    "isMultiple": false,
			    "title": "AI通过对关键词与测试库的匹配程度进行评估，可以筛选出与用户关键词相关的心理测试?",
				"jx":"匹配过程可以使用各种技术和方法，如自然语言处理、文本相似度计算等。AI可以评估用户关键词与测试库中每个测试的匹配程度，并根据匹配度的高低进行排序或筛选，以确定最相关的心理测试。",
				"dz":"../../static/bqb3.png",
				"name": "√",
				"name1": "√",
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
			    "posttime": 654318
			}
		],
      };
    },
    methods: {

	},
	onLoad(option) {
		// const params = this.$route.query
		// if (params.selectedOptions) {
		//   this.selectedOptions = JSON.parse(params.selectedOptions)
		// }
		// console.log(this.selectedOptions);
		// 延迟两秒显示loading效果
		uni.showLoading({
		  title: '加载中...',
		  mask: true
		});
		  setTimeout(() => {
			// 隐藏loading
			uni.hideLoading();
		  }, 1000);
			  
		//this.getData();
		//接受分数
		const score = option.score;
		this.score = score
		console.log(this.score);
	},
  };
</script>

<style scoped lang="scss">
  .page {
    padding: 46rpx 36rpx 306rpx;
    background-image: linear-gradient(158.8deg, #cbe3f2 44.5%, #d5afe003 100%);
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .text-wrapper {
      padding: 32rpx 0;
      background-color: #78dbff;
      border-radius: 60rpx;
      width: 252rpx;
      .text {
        color: #ffffff;
        line-height: 30rpx;
      }
    }
    .text_3 {
      margin-right: 8rpx;
      margin-top: 80rpx;
      color: #437aa1;
      font-size: 40rpx;
      font-family: SourceHanSansCN;
      line-height: 41rpx;
    }
    .button {
      position: absolute;
      left: 0;
      top: 56rpx;
      .text_4 {
        color: #437aa1;
        line-height: 38rpx;
      }
      .text_2 {
        color: transparent;
        font-size: 200rpx;
        font-family: SourceHanSansCN;
        line-height: 162rpx;
        background-image: linear-gradient(180deg, #73b9eb 50%, #b15ddeeb 100%);
        -webkit-background-clip: text;
      }
    }
    .group {
      width: 557rpx;
    }
    .space-x-20 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-left: 40rpx;
      }
    }
    .font_1 {
      font-size: 32rpx;
      font-family: SourceHanSansCN;
      font-weight: 800;
    }
    .section {
      padding: 28rpx 24rpx;
      background-color: #37a8ff38;
      border-radius: 46rpx;
      .image {
        width: 78rpx;
        height: 78rpx;
      }
      .text_5 {
        margin-right: 40rpx;
        color: #5479c3;
        font-size: 32rpx;
        font-family: SourceHanSansCN;
        line-height: 38rpx;
      }
    }
    .space-x-14 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-left: 28rpx;
      }
    }
    .list {
      padding-top: 28rpx;
      .list-item {
        padding: 24rpx;
        background-color: #f5f2f2;
        border-radius: 40rpx;
        .text-wrapper_2 {
          padding: 20rpx 0;
          background-color: #ff8d1a94;
          border-radius: 60rpx;
          width: 116rpx;
          height: 64rpx;
          .font_2 {
            font-size: 26rpx;
            font-family: SourceHanSansCN;
            line-height: 25rpx;
            font-weight: 800;
            color: #ffffff;
          }
        }
        .group_2 {
          line-height: 25rpx;
          height: 26rpx;
          .font_3 {
            font-size: 26rpx;
            font-family: SourceHanSansCN;
            line-height: 25rpx;
            color: #000000;
          }
          .text_6 {
            line-height: 24rpx;
          }
          .font_4 {
            font-size: 26rpx;
            font-family: SourceHanSansCN;
            line-height: 25rpx;
            font-weight: 800;
            color: #00ba16;
          }
		  
		  .text-correct {
		    font-size: 26rpx;
		    font-family: SourceHanSansCN;
		    line-height: 25rpx;
		    color: #000000;
		  }
		  .text-correct-green {
		    font-size: 26rpx;
		    font-family: SourceHanSansCN;
		    line-height: 25rpx;
		    font-weight: 800;
		    color: #00ba16;
		  }
		  .text-correct-red {
		    font-size: 26rpx;
		    font-family: SourceHanSansCN;
		    line-height: 17rpx;
		    font-weight: 800;
		    color: #ff5733;
		  }

          .text_7 {
            color: #ff5733;
            line-height: 17rpx;
          }
        }
        .view {
          margin-right: 4rpx;
        }
        .space-y-10 {
          & > view:not(:first-child),
          & > text:not(:first-child),
          & > image:not(:first-child) {
            margin-top: 20rpx;
          }
          .font_5 {
            font-size: 26rpx;
            font-family: SourceHanSansCN;
            line-height: 32rpx;
            color: #000000;
          }
          .section_2 {
            padding: 36rpx 0;
            background-color: #cccccc5e;
            border-radius: 42rpx;
            .group_3 {
              margin-left: 28rpx;
              margin-right: 40rpx;
              line-height: 32rpx;
              .font_7 {
                font-size: 26rpx;
                font-family: SourceHanSansCN;
                line-height: 28rpx;
                color: #0000008c;
              }
              .text_8 {
                font-size: 24rpx;
              }
              .font_6 {
                font-size: 26rpx;
                font-family: SourceHanSansCN;
                line-height: 32rpx;
                color: #0000008c;
              }
            }
          }
        }
      }
      .space-y-14 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 28rpx;
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
  }
  .space-y-16 {
    & > view:not(:first-child),
    & > text:not(:first-child),
    & > image:not(:first-child) {
      margin-top: 32rpx;
    }
  }
</style>