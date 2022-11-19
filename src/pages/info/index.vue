<template>
	<view class="content">
		<text>{{info.title}}</text>
		<rich-text :nodes="info.content"></rich-text>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				info:{}
			}
		},
		onLoad(e) {
			let newsId = e.newsId;
			if(newsId === undefined) return;
			uni.request({
				url:"https://unidemo.dcloud.net.cn/api/news/36kr/" + newsId,
				method:"GET",
				data:{},
				success:(res)=>{
					this.info = res.data;
					console.log(this.info);
				}
			})
		},
		methods: {

		}
	}
</script>

<style>
</style>
