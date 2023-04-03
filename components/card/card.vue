<template>
	<view class="box">
		<cover-image 
			class="item" 
			v-for="(item, idx) in list" 
			:src="item.url" 
			@touchmove.stop.prevent="touchMove(idx,$event)"
			@touchend="touchEnd(idx,$event)"
			:style="{left:item.left+'rpx',top:item.top+'rpx','z-index':item.zIndex}"
		>
		</cover-image>
	</view>
</template>

<script>
	export default {
		name:"card",
		props:{
			list:{
				type:Array,
				default:[],
			}
		},
		data() {
			return {

			};
		},
		methods:{
			touchMove(idx, e) {
				console.log(idx,e,e.changedTouches[0].pageX,e.changedTouches[0].pageY);
				const touchData=e.changedTouches[0];
				this.$set(this.list[idx], "z-index", 999);
				// this.$set(this.list[idx], "left", e.changedTouches[0].pageX-347);
				// this.$set(this.list[idx], "top", e.changedTouches[0].pageY-144);
				this.$set(this.list[idx], "left", touchData.pageX-347+touchData.clientX);
				this.$set(this.list[idx], "top", touchData.pageY-288-40+touchData.clientY);
				
			},
			touchEnd(idx, e) {
				console.log('end');
			}
		}
	}
</script>

<style scoped>
	.box {
		position: relative;
		background-color: palevioletred;
	}
	.item {
		position: absolute;
		width: 694rpx;
		height: 288rpx;
		border-radius: 30rpx;
	}
</style>