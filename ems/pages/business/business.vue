<template>
	<view class="content">
		<button @click="fn()">数据采集</button>
		<view>
			今天同步了{{arr.length}}次
		</view>
		<view>
			同步时间记录
		</view>
		<view>
			<uni-badge v-for="obj in arr" :text="obj" type="success"></uni-badge>
		</view>
	</view>
</template>

<script>
import uniBadge from '@dcloudio/uni-ui/lib/uni-badge/uni-badge.vue'
	export default {
		components: {uniBadge},
		data() {
			return {
				arr:[],
				
			}
		},
		onLoad() {
			uni.getStorage({
				key:"synchro",
				success:(res)=>{
					this.arr = res.data;
				}
			})
		},
		methods: {
			fn(){
				var date = new Date();
				var time = date.getHours()+":"+date.getMinutes();
				this.arr.push("同步时间"+time);
				uni.setStorage({
					key:'synchro',
					data:this.arr
				})
				
				uni.getStorage({
					key:'baseUser',
					success:(res)=>{
						var compid = res.data.compid;
						uni.request({
							url: this.url + "produceReport/initCurrentDay?compid="+compid,
							data: {
								
							},
							header: {
								'custom-header': 'login'
							},
							success: (res) => {
									title:"采集成功"
								}
							})
					}
				})
			}
		}
	}
</script>

<style>
	@import url("../../static/css/business.css");
	.content {
		text-align: center;
		height: 400upx;
		}
</style>
