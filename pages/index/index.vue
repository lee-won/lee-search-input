<template>
	<view class="content">
		<uni-search-input :iconSrc="iconSrc"></uni-search-input>
	</view>
</template>

<script>
	import uniSearchInput from '../../components/lee-search/lee-search.vue'
	export default { 
		components:{
			uniSearchInput
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

<style>
	.content {
		text-align: center;
		height: 400upx;
	}

	.logo {
		height: 200upx;
		width: 200upx;
		margin-top: 200upx;
		transform: scale(0.1);
	}

	.title {
		font-size: 36upx;
		color: #8f8f94;
	}
</style>
