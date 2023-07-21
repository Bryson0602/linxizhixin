<template>
  <view class="flex-col page space-y-10">
	  <uni-calendar 
	  	:insert="true"
	  	:lunar="true" 
	  	:start-date="'2022-3-2'"
	  	:end-date="'2024-5-20'"
		:showMonth="false"
	  	@change="change"
	  	 />
    
    <view class="flex-col section_2 space-y-28">
      <view class="flex-col items-start group_5 space-y-6">
        <text class="font_1 text_19">我的活动</text>
        <view class="section_3"></view>
      </view>
      <view class="self-center section_4"></view>
      <text class="self-center text_20">今日没有报名的活动哦</text>
    </view>
  </view>
</template>

<script>
	/**
	 * 获取任意时间
	 */
	function getDate(date, AddDayCount = 0) {
		if (!date) {
			date = new Date()
		}
		if (typeof date !== 'object') {
			date = date.replace(/-/g, '/')
		}
		const dd = new Date(date)

		dd.setDate(dd.getDate() + AddDayCount) // 获取AddDayCount天后的日期

		const y = dd.getFullYear()
		const m = dd.getMonth() + 1 < 10 ? '0' + (dd.getMonth() + 1) : dd.getMonth() + 1 // 获取当前月份的日期，不足10补0
		const d = dd.getDate() < 10 ? '0' + dd.getDate() : dd.getDate() // 获取当前几号，不足10补0
		return {
			fullDate: y + '-' + m + '-' + d,
			year: y,
			month: m,
			date: d,
			day: dd.getDay()
		}
	}
	export default {
		components: {},
		data() {
			return {
				showCalendar: false,
				info: {
					lunar: true,
					range: true,
					insert: false,
					selected: []
				}
			}
		},
		onReady() {
			this.$nextTick(() => {
				this.showCalendar = true
			})
			// TODO 模拟请求异步同步数据
			setTimeout(() => {
				this.info.date = getDate(new Date(),-30).fullDate
				this.info.startDate = getDate(new Date(),-60).fullDate
				this.info.endDate =  getDate(new Date(),30).fullDate
				this.info.selected = [{
						date: getDate(new Date(),-3).fullDate,
						info: '打卡'
					},
					{
						date: getDate(new Date(),-2).fullDate,
						info: '签到',
						data: {
							custom: '自定义信息',
							name: '自定义消息头'
						}
					},
					{
						date: getDate(new Date(),-1).fullDate,
						info: '已打卡'
					}
				]
			}, 2000)
		},
		methods: {
			open() {
				this.$refs.calendar.open()
			},
			close(){
				console.log('弹窗关闭');
			},
			change(e) {
				console.log('change 返回:', e)
				// 模拟动态打卡
				if (this.info.selected.length > 5) return
				this.info.selected.push({
					date: e.fulldate,
					info: '打卡'
				})
			},
			confirm(e) {
				console.log('confirm 返回:', e)
			},
			monthSwitch(e) {
				console.log('monthSwitchs 返回:', e)
			}
		}
	}
</script>

<style scoped lang="scss">
  .page {
    background-color: #ebebeb;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
    .section_2 {
      padding: 0 40rpx 316rpx;
      background-color: #ffffff;
      .group_5 {
        padding: 32rpx 0;
        .text_19 {
          color: #707070;
        }
        .section_3 {
          background-color: #65cbc8;
          border-radius: 60rpx;
          width: 192rpx;
          height: 8rpx;
        }
      }
      .space-y-6 {
        & > view:not(:first-child),
        & > text:not(:first-child),
        & > image:not(:first-child) {
          margin-top: 12rpx;
        }
      }
      .section_4 {
        background-color: #b4b4b4;
        border-radius: 50%;
        width: 268rpx;
        height: 268rpx;
      }
      .text_20 {
        color: #707070;
        font-size: 40rpx;
        font-family: SegoeUI-Bold;
        font-weight: 700;
        line-height: 37rpx;
      }
    }
    .space-y-28 {
      & > view:not(:first-child),
      & > text:not(:first-child),
      & > image:not(:first-child) {
        margin-top: 56rpx;
      }
    }
    .font_1 {
      font-size: 48rpx;
      font-family: SegoeUI-Bold;
      line-height: 44rpx;
      font-weight: 700;
    }
  }
  .space-y-10 {
    & > view:not(:first-child),
    & > text:not(:first-child),
    & > image:not(:first-child) {
      margin-top: 20rpx;
    }
  }
</style>
