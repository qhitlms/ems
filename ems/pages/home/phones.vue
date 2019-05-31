<template>
	<view>
		<phone-directory :phones="phones" @paramClick="paramClick"></phone-directory>
	</view>
</template>

<script>
	import phoneDirectory from '@/components/phone-directory/phone-directory.vue'
	export default {
		name:"phones",
		components:{
			phoneDirectory
		},
		data() {
			return {
				//示例数据
				phones:{
					
				}
			
			}
		},
		onLoad(){
			uni.request({
				url: this.url + "baseUser/applist", //仅为示例，并非真实接口地址。
				data: {
					
				},
				header: {
					'custom-header': 'hello' //自定义请求头信息
				},
				success: (res) => {
					this.phones=res.data;
				}
			})
		},
		methods : {
			paramClick (e) {
				console.log(e)
			}
		}
	}
</script>

<style>

</style>
