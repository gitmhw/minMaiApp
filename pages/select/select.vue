<template>
	<view>
		<view class="title">
			<view style="font-size: 1rem;font-weight: 700;">精选推荐</view>
			<view style="font-size: 0.8rem;font-weight: 700;color:#999999 ;">发现学习的乐趣</view>
		</view>
		<view v-for="typeD in typeData" :key="typeD.id">
			<my-component :title="typeD.title" :imgSrc="typeD.imgSrc" :infoText="typeD.infoText"></my-component>
		</view>
	</view>
</template>

<script>
	import MyComponent from '@/components/info.vue'

	export default {
		data() {
			return {

				typeData: [{
					id: 1,
					title: "前端开发",
					imgSrc: "/static/image/kejiONE.jpg",
					infoText: "HTML/CSS、JS/JQ",
				}, {
					id: 2,
					imgSrc: "/static/image/kejiTwo.jpeg",
					title: "亲子",
					infoText: "HTML/CSS、JS/JQ",
				}, {
					id: 3,
					imgSrc: "/static/image/kejiThree.jpg",
					title: "亲子",
					infoText: "HTML/CSS、JS/JQ",
				}]
			}
		},
		components: {
			MyComponent
		},
		methods: {

		}
	}
</script>

<style>
	.title {
		width: 100vw;
		height: 10vh;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: space-around;
	}
</style>
