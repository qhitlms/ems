<template>
	<view class="comps">
		<!-- 当前日期 -->
		<view class="cdate">{{cdate}}</view>
		<!-- 总的能耗 -->
		<view class="total">
			<view class="left">426.10</view>
			<view class="right"><view>总</view><view>折标煤</view></view>
		</view>
		<!-- 能耗分类展示 -->
		<view class="type">
			<view class="left">
				<view><image src="../../static/img/water.png"></image></view> 
				<view>418.76</view> 
				<view>水耗:吨</view>
			</view>
			<view class="middle">
				<view><image src="../../static/img/ele.png"></image></view> 
				<view>7.34</view> 
				<view>电耗:kWh</view>
			</view>
			<view class="right">
				<view><image src="../../static/img/oil.png"></image></view> 
				<view>411.43</view> 
				<view>油耗:L</view>
			</view>
		</view>
		<!-- 图表展示 -->
		<view class="buttons">
		<button class="day" :style={background:background} @click="fn('day')">日</button>
		<button class="month" :style={background:background1} @click="fn('month')">月</button>
		</view>
		<view>
			<echart></echart>
		</view>
	
	</view>
</template>

<script>
	import echart from "../charts/chart01.vue"
	export default {
		components:{echart},
		data() {
			return {
				cdate:'',
				background:'blue',
				background1:'grey'

			}
		},
		mounted() {
			var tdate = new Date();
			var month = tdate.getMonth()+1;//月份从零开始
			var day = tdate.getUTCDate();//此方法为日
			this.cdate = month+"月"+day+"日";
		},
		methods: {
			fn(type){
				// console.log("1")
				if(type=='day'){
					this.background='blue'
					this.background1='grey'
				}else if(type=='month'){
					this.background='grey'
					this.background1='blue'
				}
			}
		}
	}
</script>

<style>
	
</style>
