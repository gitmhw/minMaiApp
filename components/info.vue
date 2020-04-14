<template>
	<view class="infoBox">
		<image style="width: 80vw;height: 30vh;" :src="imgSrc"></image>
		<text style="font-size: 1rem;font-weight: 700;">{{title}}</text>
		<text style="font-size: 0.8rem;font-weight: 700;color:#999999 ;">{{infoText}}</text>
	</view>
</template>

<script>
	export default {
		name: "my-component",
		// 属性
		props: {
			title: {
				type: String, // 属性类型
				default: "你好" // 默认值
			},
			imgSrc: {
				type: String, // 属性类型
			},
			infoText: {
				type: String, // 属性类型
				default: "学习使人快乐" // 默认值
			}
		}
	}
</script>
<style>
	// 组件样式
	.infoBox {
		width: 80vw;
		height: 40vh;
		margin: auto;
		display: flex;
		flex-direction: column;
		margin-top: 4vh;
	}
</style>
