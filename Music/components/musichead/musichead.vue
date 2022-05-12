<template>
	<view class="music-head" :style="{color : color}">
		<view class="music-head-icon" v-if="icon" :class="{ 'music-head-iconblack' : iconblack}">
			<text class="iconfont iconzuojiantou-copy" @tap="handleToBack"></text> | <text class="iconfont iconshouye" @tap="handleToHome"></text>
		</view>
		{{title}}
	</view>
</template>

<script>
	export default {
		name:"musichead",
		data() {
			return {
				
			};
		},
		props:['title','icon','color','iconblack'],
		methods:{
			handleToBack(){
				uni.navigateBack()
			},
			handleToHome(){
				uni.navigateTo({
					url:'/pages/index/index'
				})
			}
		}
	}
</script>

<style scoped>
.music-head{ height:75px; text-align: center; line-height: 80px; font-size:16px; color:black; overflow: hidden; position: relative;}
.music-head-icon{ width:97px; height:31px; background:rgba(0,0,0,0.4); border-radius: 15px; position: absolute; left:10px; top:25px; line-height: 31px; display: flex; justify-content: space-evenly; color:white;}

.music-head-iconblack{ color:black; background:white; border:1px black solid;}
</style>
