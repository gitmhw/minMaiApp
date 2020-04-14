<template>
	<view>
		<view class="uni-padding-wrap">
			<view class="page-section swiper">
				<view class="page-section-spacing">
					<swiper :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration">
						<swiper-item>
							<image src="../../static/image/kejiONE.jpg" mode="heightFix"></image>
						</swiper-item>
						<swiper-item>
							<image src="../../static/image/kejiTwo.jpeg" mode="heightFix"></image>
						</swiper-item>
						<swiper-item>
							<image src="../../static/image/kejiThree.jpg" mode="heightFix"></image>
						</swiper-item>
					</swiper>
				</view>
			</view>
		</view>
		<view class="classify">
			课件类别：
		</view>
		<view class="typeBox">
			<view class="typeSmallBox" v-for="typeD in typeData" :key="typeD.id">
				<image class="imgs" :src="typeD.src"></image>
				<view>{{typeD.title}}</view>
			</view>
		</view>
		<view>
			<video style="width: 100vw;height: 30vh;" id="myVideo" :auto-pause-if-navigate="true" :autoplay="true" src="https://img.cdn.aliyun.dcloud.net.cn/guide/uniapp/%E7%AC%AC1%E8%AE%B2%EF%BC%88uni-app%E4%BA%A7%E5%93%81%E4%BB%8B%E7%BB%8D%EF%BC%89-%20DCloud%E5%AE%98%E6%96%B9%E8%A7%86%E9%A2%91%E6%95%99%E7%A8%8B@20181126.mp4"
			 @error="videoErrorCallback" :danmu-list="danmuList" enable-danmu danmu-btn controls></video>
		</view>
	</view>

</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello World',
				indicatorDots: false,
				autoplay: true,
				interval: 2000,
				duration: 500,
				typeData: [{
					id: 1,
					src: "../../static/image/mineIcon.png",
					title: "亲子"
				}, {
					id: 2,
					src: "../../static/image/mineIcon.png",
					title: "亲子"
				}, {
					id: 3,
					src: "../../static/image/mineIcon.png",
					title: "亲子"
				}, {
					id: 4,
					src: "../../static/image/mineIcon.png",
					title: "亲子"
				}]
			}
		},
		onReady: function(res) {
			this.videoContext = uni.createVideoContext('myVideo')
		},
		methods: {

		}
	}
</script>

<style>
	.classify {
		height: 10vh;
		width: 80vw;
		margin-left: 10vw;
		line-height: 10vh;
	}

	.typeBox {
		width: 88vw;
		height: 10vh;
		margin: auto;
		display: flex;
		align-items: center;
		justify-content: space-around;
	}

	.typeSmallBox {
		width: 22vw;
		height: 10vh;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: space-around;
	}

	.imgs {
		width: 15vw;
		height: 5vh;
	}
</style>
