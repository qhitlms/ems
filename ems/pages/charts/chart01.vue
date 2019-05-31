<template>
	<view class="body" scroll-y="true" >
		<!-- 注意：class="chart-father" 必不可少，否则图表显示不出来 -->
		<view class="chart-father">
			<mpvue-echarts :echarts="echarts" :onInit="lineInit" canvasId="line"  />
		</view>
	</view>
</template>

<script>
	import * as echarts from '../../components/demo-echart/echarts/echarts.simple.min.js';
	import mpvueEcharts from '../../components/demo-echart/mpvue-echarts/src/echarts.vue';
	var lineChart=null;
	
	
	export default {
	    data() {
	        return {
				echarts: echarts
	        }
	    },
		onLoad:function () {
		},
		methods: {
			
			lineInit(canvas, width, height) {
				lineChart = echarts.init(canvas, null, {
					width: width,
					height: height
				})
				canvas.setChart(lineChart)
				var option = {
					xAxis: {
						type: 'category',
						data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
					},
					yAxis: {
						type: 'value'
					},
					series: [{
						data: [820, 932, 901, 934, 1290, 1330, 1320],
						type: 'line'
					}]
				}
				lineChart.setOption(option)
				return lineChart
			}
			
			
		},
		components: {
			mpvueEcharts
		},
		
	}
</script>

<style>
	.chart-father{
		display: flex;
		margin-top: -10upx;
		width: 100%;
		height: 500upx;
		background: #F4F4F4;
		justify-content: center;
	}
	
</style>
