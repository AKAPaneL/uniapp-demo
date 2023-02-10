<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view>
			<text class="title">{{title}}</text>
		</view>
		<button @click="setTitle">点击修改标题</button>
		<progress-vue></progress-vue>
		<w-loading text="加载中.." mask="true" click="true" ref="loading"></w-loading>
		<!-- #ifdef MP-WEIXIN -->
		<uni-badge text="1"></uni-badge>
		<!-- #endif -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				value:'1'
			}
		},
		onLoad() {
			uni.showToast({
				title:'启动成功',
				icon:'success',
				duration:1500
			})
		},
		onReady() {
			this.$refs.loading.open()
		},
		methods: {
			setTitle(){
				uni.setNavigationBarTitle({
					title:'首页'
				})
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin: 200rpx auto 50rpx auto;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
