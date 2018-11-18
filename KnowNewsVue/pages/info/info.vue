<template>
	<rich-text class="richText" nodes="strings"></rich-text>
	<link rel="stylesheet" href="">
</template>

<script>
	export default {
		data(){
			return{
				strings : ''
			}
		}
	},
	onLoad: function(e) {
		uni.request({
			url: 'https://news-at.zhihu.com/api/4/news/' + e.newsid,
			method: 'GET',
			data: {},
			success: res => {
				this.strings = res.body;
			},
			fail: () => {},
			complete: () => {}
		});
	}
</script>

<style>

</style>
