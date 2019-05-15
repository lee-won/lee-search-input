<template>
	<view class="content">
		<lee-search :iconSrc="iconSrc">
			<!-- <template v-slot:icon>
				<view class="icon-wrap">
					<image class="icon"  mode="aspectFit"  src="../../static/lee-search/icon_clear.png"></image>
				</view>
			</template> -->
		</lee-search>
	</view>
</template>

<script>
	import leeSearch from '../../components/lee-search/lee-search.vue'
	export default { 
		components:{
			leeSearch
		},
		data() {
			return {
				iconSrc: {
					logo: '../../static/lee-search/icon_search.png',
					voice: '../../static/lee-search/icon_voice.png',
					scan: '../../static/lee-search/icon_scan.png',
					clear:'../../static/lee-search/icon_clear.png'
				}
			}
		},
		onLoad() {

		},
		methods: {
			scan(data){
				console.log(data)
			}
		}
	}
</script>

<style lang="scss">
	.content {
		text-align: center;
		height: 400upx;
		.icon-wrap{
			position:relative;
			height:60upx;
			top:0;
			box-sizing: border-box;
			.icon{
				width:60upx;
				height:60upx;
				padding:10upx;
				box-sizing: border-box;
			}
		}
	}

	
</style>
