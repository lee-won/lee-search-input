<template>
	<view class="content">
		<uni-search-input :inputAttr="inputStyle" :voiceAttr="voiceAttr" :btnAttr="btnAttr" :iconSrc="iconSrc"   @scan="scan"></uni-search-input>
	</view>
</template>

<script>
	import uniSearchInput from '../../components/lee-search-input/lee-search-input.vue'
	export default { 
		components:{
			uniSearchInput
		},
		data() {
			return {
				inputStyle: {
					placeholderText: 'ahhahfh'
				},
				voiceAttr:{},
				btnAttr:{},
				iconSrc: {
					logo: '../../static/icon_search.png',
					voice: '../../static/icon_voice.png',
					scan: '../../static/icon_scan.png',
					clear:'../../static/icon_clear.png',
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
