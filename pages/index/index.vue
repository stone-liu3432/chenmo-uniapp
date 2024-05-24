<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
		</view>
		<button @click="pingTest">ping</button>
		<button @click="pingSyncTest">pingSync</button>
	</view>
</template>

<script>
	import {
		ping,
		pingSync
	} from "@/uni_modules/chenmo-ping"
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {
			pingTest() {
				ping({
					addr: "192.168.88.1",
					success: res => {
						console.log(res);
					},
					fail: e => {
						console.log(e);
					}
				})
			},
			pingSyncTest() {
				const res = pingSync({
					addr: "www.baidu.com",
				})
				console.log(res);
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
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
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