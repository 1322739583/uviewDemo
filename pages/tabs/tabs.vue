<template>
	<view>
		<u-tabs :list="list1" @click="click" :activeStyle="activeStyle"></u-tabs>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list1: [
					{name: '关注'}, 
					{name: '推荐'}, 
					{name: '电影'} 
				],
				activeStyle: {
					color: '#ffccff',
					border: '1px solid #ffcccc',
					padding: '1rpx 8px',
					'border-radius':'5px'
				}
			}
		},
		methods: {
			click(item) {
				console.log('item', item);
			}
		}
	}
</script>

<style lang="scss">
	// .activeStyle {
	// 	background-color: #ccffcc;
	// 	color: #aa00ff;
	// }

	// /deep/.u-tabs__wrapper__nav__item__text {
	// 	border: 1px solid #ffccff;
	// 	border-radius: 5px;
	// 	padding: 1rpx 8px;
	// }

	// /deep/.u-tabs__wrapper__nav__line {
	// 	display: none;
	// 	position: relative;
	// 	width: 0;
	// 	height: 0;
	// 	z-index: -1;
	// }
</style>
