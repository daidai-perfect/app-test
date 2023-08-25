<template>
	<div class="page">
		<div class="count">{{count}}</div>
		<audio ref='audio'>
			<source src="/muyu.mp3" />
		</audio>
		<img :class="imgActive?'img-active':''" src="../assets/muyu.png" alt="" @click="clickMuyu()">
		<div class="text" :class="imgActive?'text-active':''">{{currentTips}}</div>
		<div class="tip-text">
			<div class="item" v-for="item in list" :key="item.type" @click="changeType(item)">
				<span :class="currentType==item.type?'type-active':''">{{item.type}}</span>
			</div>
		</div>
	</div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  setup(props, ctx) {
		const count = ref(0)
		const audio:any = ref(null)
		const imgActive = ref(false)
		const currentType = ref('功德')
		const currentTips = ref('功德 +1')
		const clickMuyu = ()=>{
			audio.value.play()
			if (currentType.value=='功德') {
				count.value ++
			}else if (currentType.value=='金钱') {
				count.value +=100
			}else{
				count.value --
			}
			imgActive.value = true
			setTimeout(() => {
				imgActive.value = false
			}, 300);
		}
		const list = [
			{
				type:'功德',
				typeTips:'功德 +1'
			},
			{
				type:'金钱',
				typeTips:'金钱 +100'
			},
			{
				type:'抗疫',
				typeTips:'阳性 -1'
			},
			{
				type:'bug',
				typeTips:'bug -1'
			}
		]
		const changeType =(item:any)=>{
			count.value = 0
			currentType.value = item.type
			currentTips.value = item.typeTips
		}
		return {
			changeType,
			count,
			clickMuyu,
			imgActive,
			currentType,
			currentTips,
			audio,
			list
		}
  }
})
</script>
<style lang="less" scoped>
@keyframes textMove{
	from{
		top: 200px;
		opacity: 1;
	}
	to{
		top: 180px;
		opacity: 1;
	}
}
@keyframes muyuScale{
	0%{
		transform: scale(1);
	}
	50%{
		transform: scale(0.95);
	}
	100%{
		transform: scale(1);
	}
}
*{
	padding: 0;
	margin: 0;
}
.page{
	width: 100%;
	height: 100vh;
	padding-top: 50px;
	text-align: center;
	background: #000;
	position: relative;
	.count{
		color: #fff;
		font-size: 30px;
	}
	img{
		width: 40%;
		margin-top: 80px;
	}
	.img-active{
		animation: muyuScale 300ms;
	}
	.text{
		color: #fff;
		position: absolute;
		right:200px;
		top: 200px;
		opacity: 0;
		font-size: 20px;
	}
	.text-active{
		animation: textMove 300ms;
	}
	.tip-text{
		color: #fff;
		position: absolute;
		left: 100px;
		top: 100px;
		.item{
			cursor: pointer;
			margin-top: 10px;
		}
	}
	.type-active{
		color: yellow;
	}
}

</style>