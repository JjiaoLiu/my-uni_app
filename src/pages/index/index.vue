<template>
	<view class="content">
		<view class="uni-media">
			<view class="uni-media-list" @tap="openInfo(item)" 
			v-for="(item,index) in news" :key="item.post_id" data-newid="item.post_id">
				<view class="uni-media-list-img">
					<img :src="item.author_avatar" class="responsive" alt="" srcset="">
				</view>
				<view class="uni-media-list-content">
					<view class="uni-media-list-content-top">
						{{item.title}}
					</view>
					<view class="uni-media-list-content-bottom">
						{{item.created_at}}
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				news: []
			}
		},
		onLoad() {
			uni.request({
				url:"https://unidemo.dcloud.net.cn/api/news",
				method:"GET",
				data:{},
				success:(res)=>{
					this.news = res.data
				}
			})
		},
		methods: {
			openInfo(news){
				uni.navigateTo({
					url:'/pages/info/index?newsId='+news.post_id
				})
			}
		}
	}
</script>

<style lang="scss">
	@import "index.scss";
</style>