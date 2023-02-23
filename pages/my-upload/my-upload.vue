<template>
	<view>
		<view class="filelist-wrapper" v-for="fileList">
			
		</view>
		<button @tap="chooseFile">上传文件</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				fileList:""
			}
		},
		methods: {
			chooseFile(){
				uni.chooseImage({
				    success() {
				    	
				    }
					complete() {
						
					}
				})
			}
		}
	}
</script>

<style>

</style>
