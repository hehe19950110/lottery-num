<template>
	<view class="content">

		<view class="panel">
			<text>{{num}}</text>
		</view>

		<view class="button-area">
			<button v-show="isLoading" @click="start"> 开始抽奖 </button>
			<button v-show="!isLoading" @click="stop"> 结束抽奖 </button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				num: 8,
				min:0,//含最小值
				max:100,//不含最大值
				interval:100,//毫秒
				isLoading: true,
				clock:null,

			}
		},
		onLoad() {

		},
		onShow(){
			let setting = uni.getStorageSync('setting') || { max:100, min:0, interval:20 }
			this.max = setting.max
			this.min = setting.min
			this.interval = setting.interval
		},
		methods: {
			start(){
				this.isLoading = false
				this.clock = setInterval(()=> {
					this.num = this.getRandomNum()
				},this.interval)
			},
			stop(){
				clearInterval(this.clock)
				this.isLoading = true
			},
			
			getRandomNum(){
				return parseInt(this.min) + Math.floor(Math.random()*(parseInt(this.max) - parseInt(this.min)))
			},

		}
	}
</script>

<style lang="scss">
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	
	.panel {
		width: 60vw;
		height: 30vh;
		margin: 10vh;
		border-radius: 28rpx;
		display: flex;
		justify-content: center;
		align-items: center;
		border: 1rpx solid $uni-border-color;
		box-shadow:0px 0px 15px 0px rgba(0,0,0,0.5);
		text {
			font-size: 180rpx;
		}
	}
	
	.button-area{

	}


</style>
