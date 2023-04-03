<template>
	<view class="content">
		<card :list="imageList"></card>
	</view>
</template>

<script>
import card from "../../../components/card/card.vue";

import img1 from '../../../images/1.png';
import img2 from '../../../images/2.png';
import img3 from '../../../images/3.png';
import img4 from '../../../images/4.png';
import img5 from '../../../images/5.png';
import img6 from '../../../images/6.png';
import img7 from '../../../images/7.png';
import img8 from '../../../images/8.png';
export default {
	components:{
		card
	},
	data() {
		return {
			title: 'Hello',
			imageList:[
				{name:"img1",url:img1,left:0,top:40,zIndex:3},
				{name:"img2",url:img2,left:20,top:20,zIndex:2},
				{name:"img3",url:img3,left:40,top:0,zIndex:1},
				{name:"img4",url:img4,left:40,top:0,zIndex:1},
				{name:"img5",url:img5,left:40,top:0,zIndex:1},
				{name:"img6",url:img6,left:40,top:0,zIndex:1},
				{name:"img7",url:img7,left:40,top:0,zIndex:1},
				{name:"img8",url:img8,left:40,top:0,zIndex:1},
			],
		};
	},
	onLoad() {},
	methods: {}
};
</script>

<style>
.content {
	text-align: center;
	height: 400upx;
	margin-top: 200upx;
}
</style>
