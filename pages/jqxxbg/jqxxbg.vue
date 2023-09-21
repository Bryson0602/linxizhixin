<template>
  <view class="flex-col page space-y-16">
    <view class="flex-col relative">
      <view class="flex-col justify-start items-center self-start text-wrapper">
        <text class="font_1 text">机器学习测试</text>
      </view>
      <text class="self-end text_3">/7道</text>
      <view class="flex-row items-baseline button group space-x-20">
        <text class="flex-auto font_1 text_4">此次测验，您一共答对了：</text>
        <text class="shrink-0 text_2">{{this.score}}</text>
      </view>
    </view>
    <view class="flex-col">
      <view class="flex-row items-center section space-x-14">
        <image
          class="shrink-0 image"
          src="../../static/newai.png"
        />
        <text class="flex-auto text_5">查看解析，发现问题的所在，继续加油哦~</text>
      </view>
      <view class="flex-col list space-y-13">
        <view class="flex-col list-item space-y-14" v-for="(item, index) in items" :key="index">
          <view class="flex-row justify-between items-center">
            <view class="flex-col justify-start items-center text-wrapper_2"><text class="font_2">第{{item.id}}题</text></view>
            <view class="group_2 view">
              <text class="font_3 text_6">正确答案：</text>
              <text :class="['font_4', item.name === '√' ? 'text-correct-green' : 'text-correct-red']">{{item.name}}</text>
              <text class="font_3">，你的答案</text>
              <text :class="['font_4', item.name1 === '√' ? 'text-correct-green' : 'text-correct-green']">{{item.name1}}</text>
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
			    "title": "监督学习中，训练数据应包括哪些部分？ A) 输入特征和输出变量 B) 输出变量和模型参数 C) 输入特征和模型参数",
				"jx":"在监督学习中，训练数据应该包括输入特征和对应的输出变量。输入特征是用来描述和表示问题的特征，在训练过程中作为模型的输入；输出变量是要预测或分类的目标变量，在训练过程中作为模型的输出。",
				"dz":"../../static/zbts.png",
				"name": "A",
				"name1": "A",
			},
			{
			    "_id": "64c4abe18b0da41af06b8371",
			    "id": 2,
			    "isMultiple": false,
			    "title": "深度学习涉及什么？ A) 模拟人类学习过程的机器学习算法 B) 通过训练大量数据提高性能的神经网络技术 C) 通过集成多个模型提高性能的机器学习技术",
				"jx":"深度学习是一种机器学习算法，通过训练大量数据来提高性能的神经网络技术。它可以通过多层次的神经元结构进行信息的传递和处理，从而实现复杂的模式识别和预测任务。",
				"dz":"../../static/bqb1.png",
				"name": "B",
				"name1": "C",
			},
			{
			    "_id": "64c4ac129755e344abedd648",
			    "id": 3,
			    "isMultiple": false,
			    "title": "什么是梯度下降？ A) 一种优化算法，用于更新模型参数以最小化损失函数 B) 一种特征选择算法，用于减少数据维度 C) 一种评估模型性能的统计指标",
				"jx":"梯度下降是一种优化算法，用于更新模型参数以最小化损失函数。在机器学习中，我们通过定义一个损失函数来衡量模型的预测结果与真实值之间的差异，不断调整参数的数值，使得损失函数逐渐减小，从而找到最优的模型参数。",
				"dz":"../../static/bqb2.png",
				"name": "A",
				"name1": "B",
			},
			{
			    "_id": "64c4ac3555b3378257a78ca5",
			    "id": 4,
			    "isMultiple": false,
			    "title": "什么是正则化（Regularization）？ A) 一种特征选择算法，用于减少数据维度 B) 一种评估模型性能的统计指标 C) 一种用于控制模型复杂度的技术",
				"jx":"正则化是一种用于控制模型复杂度的技术。在机器学习中，构建的模型能够对未见过的数据进行准确的预测，而过于复杂的模型可能会导致过拟合现象。正则化通过在损失函数中添加一个惩罚项，限制模型参数的数值范围。",
				"dz":"../../static/bqb3.png",
				"name": "C",
				"name1": "C",
			},
			{
			    "_id": "64c4ac3555b3378257a78ca5",
			    "id": 5,
			    "isMultiple": false,
			    "title": "在监督学习中，什么是回归问题（Regression）？ A) 预测离散的类别或标签 B) 预测连续的数值 C) 对数据进行分类",
				"jx":"回归问题是监督学习中的一种任务，它是用于预测连续的数值。与分类问题不同，回归问题的输出是一个连续的数值，可以是实数或者整数，用于对目标变量进行预测。",
				"dz":"../../static/bqb3.png",
				"name": "B",
				"name1": "B",
			},
			{
			    "_id": "64c4ac3555b3378257a78ca5",
			    "id": 6,
			    "isMultiple": false,
			    "title": "以下哪个算法适用于处理文本数据？ A) 支持向量机（SVM） B) K均值聚类 C) 主成分分析",
				"jx":"支持向量机（SVM）是一种常用于处理文本数据的算法。SVM通过将文本数据映射到高维空间，并构建一个最优的超平面来实现分类任务。在文本分类、情感分析等文本处理任务中，SVM具有较好的性能和泛化能力。",
				"dz":"../../static/bqb3.png",
				"name": "A",
				"name1": "A",
			},
			{
			    "_id": "64c4ac3555b3378257a78ca5",
			    "id": 7,
			    "isMultiple": false,
			    "title": "以下哪个算法常用于异常检测？ A) 支持向量机（SVM） B) 决策树 C) K均值聚类",
				"jx":"支持向量机常用于异常检测。SVM在异常检测中可以利用其边界拟合的能力，将正常样本与异常样本区分开来。通过找到最优的超平面，SVM可以识别和检测出数据中的异常点或异常模式。",
				"dz":"../../static/bqb3.png",
				"name": "A",
				"name1": "A",
			}
		],
      };
    },
    methods: {

	},
	onLoad(option) {
		const params = this.$route.query
		if (params.selectedOptions) {
		  this.selectedOptions = JSON.parse(params.selectedOptions)
		}
		console.log(this.selectedOptions);
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
    background-image: linear-gradient(100deg, #ffffff 44.5%, #ffffff 100%);
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .text-wrapper {
      padding: 32rpx 0;
      background-color: #ffbe6f;
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
      color: #7a816d;
      font-size: 40rpx;
      font-family: SourceHanSansCN;
      line-height: 41rpx;
    }
    .button {
      position: absolute;
      left: 0;
      top: 56rpx;
      .text_4 {
        color: #7a816d;
        line-height: 38rpx;
      }
      .text_2 {
        color: transparent;
        font-size: 200rpx;
        font-family: SourceHanSansCN;
        line-height: 162rpx;
        background-image: linear-gradient(180deg, #fab951 50%, #fe9b73eb 100%);
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
      background-color: #f7e5d8ff;
      border-radius: 46rpx;
      .image {
        width: 78rpx;
        height: 78rpx;
      }
      .text_5 {
        margin-right: 40rpx;
        color: #8b817a;
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
        background-color: #e9f0ff;
        border-radius: 40rpx;
        .text-wrapper_2 {
          padding: 20rpx 0;
          background-color: #77ccf3ff;
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
            color: #3f4246;
          }
          .section_2 {
            padding: 36rpx 0;
            background-color: #ffffff;
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