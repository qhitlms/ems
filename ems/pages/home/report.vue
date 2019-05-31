<template>
	<view class="content">
		<!-- <table01></table01> -->
		<uni-list>
			<uni-list-item title="港口能耗对比" @click='fn(1)' show-extra-icon="true"
			  :extra-icon="{color:'#4cd964',size:'22',type:'list'}"show-badge="true" badge-text="12"></uni-list-item>
			<uni-list-item title="流程作业量对比" @click='fn(2)' show-extra-icon="true"
			    :extra-icon="{color:'#4cd964',size:'22',type:'list'}"show-badge="true" badge-text="12"></uni-list-item>
			<uni-list-item title="成本核算信息" @click='fn(3)' show-extra-icon="true"
				  :extra-icon="{color:'#4cd964',size:'22',type:'list'}"show-badge="true" badge-text="12"></uni-list-item>
			
		</uni-list>
	</view>
</template>

<script>
	import table01 from "../table/table01.vue"
	import uniList from '@dcloudio/uni-ui/lib/uni-list/uni-list.vue'
	import uniListItem from '@dcloudio/uni-ui/lib/uni-list-item/uni-list-item.vue'
	export default {
		components:{uniList,uniListItem,table01},
		data() {
			return {
				
			}
		},
		mounted(){
			
		},
		methods: {
			fn(index){
				if(index==3){
				uni.navigateTo({
					url:"../table/table02"
				})
			 }
			 else if(index==1){
				 uni.navigateTo({
				 	url:"../charts/chart03"
				 })
			 }
			}
		}
	}
</script>

<style>
	.content {
		text-align: center;
		height: 400upx;
	}
  
</style>
