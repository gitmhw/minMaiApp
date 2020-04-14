<template>
	<view class="content" v-if="model">
		<view class="contentBox">
			<view class="smallBox">
				昵称：
			</view>
			<view class="smallBox">
				{{userInfo.nickName}}
			</view>
		</view>
		<view class="contentBox">
			<view class="smallBox">
				微信头像：
			</view>
			<view class="smallBox">
				<image class="logo" :src="userInfo.avatarUrl"></image>
			</view>
		</view>
		<view class="contentBox">
			<view class="smallBox">
				籍贯：
			</view>
			<view class="smallBox">
				{{userInfo.province}}
			</view>
		</view>
		<view class="contentBox">
			<view class="smallBox">
				性别：
			</view>
			<view class="smallBox">
				{{userInfo.gender == 1 ? "男" : "女"}}
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				name: "admin",
				userInfo: [],
				model: false
			}
		},
		onLoad() {
			let vm = this;
			uni.login({
				provider: 'weixin',
				success: function(loginRes) {
					// 获取用户信息
					uni.getUserInfo({
						provider: 'weixin',
						success: function(infoRes) {
							console.log(infoRes.userInfo)
							vm.userInfo = infoRes.userInfo
							vm.model = true;
						}
					});
				}
			});
		},
		methods: {

		}
	}
</script>

<style>
	.content {
		height: 60vh;
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
	}

	.contentBox {
		height: 15vh;
		width: 80vw;
		margin: auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
		border-bottom: 2rpx #C0C0C0 solid;
	}

	.logo {
		width: 12vh;
		height: 12vh;
		border-radius: 50%;
	}
</style>
