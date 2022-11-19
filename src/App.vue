<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	* {
		box-sizing: border-box;
		line-height: 1.3;
	}
	/*每个页面公共css */
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		width: 750rpx;
		margin: 0 auto;
		padding: 20rpx;
	}
	.responsive {
		width: 100%;
	}
</style>
