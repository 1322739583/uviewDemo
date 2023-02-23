<template>
	<view>
		    <!-- 说明：这个组件的自定义功能应该是非常差的，例如你想同时展示文件名和图片好像是很难实现的。 -->
			<!-- 1.基本使用 -->
<!-- 			<u-upload
				:fileList="fileList1"
				@afterRead="afterRead"
				@delete="deletePic"
				name="1"
				multiple
				:maxCount="10"
			></u-upload> -->
			<!-- 2.自定义样式 -->
			<u-upload
				:fileList="fileList1"
				@afterRead="afterRead"
				@delete="deletePic"
				name="1"
				multiple
				:maxCount="10"
				width="250"
				height="150"
			>
				<image src="https://cdn.uviewui.com/uview/demo/upload/positive.png" 
				mode="widthFix" style="width: 150px;height: 100px;"></image>
				<text>filename</text>
			</u-upload>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				fileList1: [],
			}
		},
		methods:{
			// 删除图片
			deletePic(event) {
				this[`fileList${event.name}`].splice(event.index, 1)
			},
			// 新增图片
			async afterRead(event) {
				// 当设置 multiple 为 true 时, file 为数组格式，否则为对象格式
				let lists = [].concat(event.file)
				let fileListLen = this[`fileList${event.name}`].length
				lists.map((item) => {
					this[`fileList${event.name}`].push({
						...item,
						status: 'uploading',
						message: '上传中'
					})
				})
				for (let i = 0; i < lists.length; i++) {
					const result = await this.uploadFilePromise(lists[i].url)
					let item = this[`fileList${event.name}`][fileListLen]
					this[`fileList${event.name}`].splice(fileListLen, 1, Object.assign(item, {
						status: 'success',
						message: '',
						url: result
					}))
					fileListLen++
				}
			},
			uploadFilePromise(url) {
				return new Promise((resolve, reject) => {
					let a = uni.uploadFile({
						url: 'http://192.168.2.21:7001/upload', // 仅为示例，非真实的接口地址
						filePath: url,
						name: 'file',
						formData: {
							user: 'test'
						},
						success: (res) => {
							setTimeout(() => {
								resolve(res.data.data)
							}, 1000)
						}
					});
				})
			},
		},
		onLoad() {
			 
		}

	}
</script>

<style lang="scss">
   // 这个是图片列表的wrapper
   /deep/.u-upload__wrap__preview{
	   width: 100px;
	   height: 70px;
   }
</style>
