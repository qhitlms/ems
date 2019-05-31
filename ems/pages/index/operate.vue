<template>
	<view class="content">
		<view class="circular">
			<view class="f1">29</view><view class="f11">天</view>
			<view class="f2">安全用电</view>
			<view class="f3">/</view>
			<view class="f4">10</view><view class="f44">条</view>
			<view class="f5">异常警告</view>
		</view>
		<!-- 分割线 -->
		
		<!-- 列表 -->
		<view class="unilist">
			<uni-list>
				<uni-list-item title="流动fm1" note="今天的作业量" show-badge="true" badge-text="作业量"></uni-list-item>
				<uni-list-item title="流动fm2" note="今天的作业量" show-badge="true" badge-text="作业量"></uni-list-item>
				<uni-list-item title="流动fm3" note="今天的作业量" show-badge="true" badge-text="作业量"></uni-list-item>
				<uni-list-item title="流动fm4" note="今天的作业量" show-badge="true" badge-text="作业量"></uni-list-item>
			</uni-list>
		</view>
	</view>
</template>

<script>
	import uniList from "@dcloudio/uni-ui/lib/uni-list/uni-list.vue"
	import uniListItem from "@dcloudio/uni-ui/lib/uni-list-item/uni-list-item.vue"
	export default {
		components: {
			uniList,uniListItem
		},
		data() {
			return {

			}
		},
		mounted() {
			
		},
		methods:{
			
		}
	}
</script>

<style>
	/* .content {
		margin-top: 50upx;
		text-align: center;
		height: 400upx;
	}

	.title {
		font-size: 36upx;
	} */
	@import url("../../static/css/operate.css");
</style>
