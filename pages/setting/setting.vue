<template>

	<view class="content">
		<view class="list">
		<view class="uni-form-item uni-column">
			<view class="title">最大值（数字）</view>
			<input class="uni-input" v-model="max" type="number" placeholder="最大值" />
		</view>
		<view class="uni-form-item uni-column">
			<view class="title">最小值（数字）</view>
			<input class="uni-input"  v-model="min" type="number" placeholder="最小值" />
		</view>
		<view class="uni-form-item uni-column">
			<view class="title">时间间隔（毫秒）</view>
			<input class="uni-input"  v-model="interval" type="number" placeholder="时间间隔" />
		</view>
		</view>
		
		<view class="button-area">
			<button @click="onHold">保存</button>
		</view>
	</view>

</template>

<script>
	export default {
		data() {
			return {
				max:100,
				min:0,
				interval:20,
			}
		},
		created(){
			let setting = uni.getStorageSync('setting') || { max:100, min:0, interval:20 }
			this.max = setting.max
			this.min = setting.min
			this.interval = setting.interval
		},
		methods: {
			onHold(){
				let setting = { max:this.max, min:this.min, interval:this.interval }
				uni.setStorageSync('setting', setting);
			}
		}
	}
</script>

<style lang="scss">
	.uni-form-item {
		margin: 5vh;
	}

	.title {
		font-size: 30rpx;
		font-weight: 600;
		margin-bottom: 1vh;
	}

	.uni-input {
		border-bottom: 1px solid $uni-border-color;
		font-size: 26rpx;
		margin-top: 10rpx;
	}
	.button-area {
		margin-top: 10vh;
		display: flex;
		justify-content: center;
		button {
			width: 30vw;
		}
	}
</style>
