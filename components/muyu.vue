<template>
  <div class="page">
    <div class="count">{{count}}</div>
    <img :class="['img', {'img-active': imgActive}]" src="https://clemmensen.top/static/muyu.png" alt="" @click="clickMuyu">
    <div :class="['tips', { 'tips-active': tipsActive }]">
      {{tips}}
    </div>
    <audio controls ref="audio" class="aud">
      <source src="https://clemmensen.top/static/muyu.mp3" />
    </audio>
    <audio controls ref="bgm" loop="loop" class="aud">
      <source src="https://clemmensen.top/static/28297622582.mp3" />
    </audio>
    <div class="txt-right">
      <div :class="['txt', {'txt-active': index === sel}]" v-for="(item, index) in list" :key="index" @click="changeIndex(index)">
        {{item.type}}
      </div>
    </div>
    <div class="cover" v-if="showCover">
      <div class="lyric">
        睡到僧廊响木鱼，庄周蝴蝶两蘧蘧。
      </div>
      <div class="start" @click="start">Start</div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  setup(props, ctx) {
		const showCover = ref(true)
		const count = ref(0)
		const tips = ref('功德 +1')
		const tipsActive = ref(false)
		const imgActive = ref(false)
		const time = ref(300)
		const audio:any = ref(null)
		const bgm:any = ref(null)
		const sel = ref(0)
		const list = ref([
			{
				type: '功德',
				tips: '功德 +1'
			},
			{
				type: '抗疫',
				tips: '阳性 -1'
			},
			{
				type: 'Bug',
				tips: 'Bug -1'
			},
		])

		const start=()=> {
			showCover.value = false
			playBGM()
		}
		const playBGM=()=> {
			bgm.value.play()
		}
		const playMuyu=()=> {
			audio.value.play()
		}
		const clickMuyu = ()=> {
			count.value ++
			tipsActive.value = true
			imgActive.value = true
			setTimeout(() => {
				tipsActive.value = false
				imgActive.value = false
			}, time.value)
			playMuyu()
		}
		const changeIndex =(index:any)=> {
			sel.value = index
			tips.value = list.value[sel.value].tips
		}
		return {
      imgActive,
			showCover,
			count,
			tips,
			tipsActive,
			time,
			audio,
			bgm,
			sel,
			list,
			start,
			playBGM,
			playMuyu,
			clickMuyu,
			changeIndex
		}
	}
})
</script>
<style lang="less" scoped>
*{
  margin: 0;
  padding: 0;
}
@keyframes textMove {
  from {
    top: 20%;
    opacity: 1;
  }
  to {
    top: 18%;
    opacity: 0;
  }
}
@keyframes muyuScale {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(0.95);
  }
  100% {
    transform: scale(1);
  }
}
.page{
  background-color: #000;
  height: 100vh;
  width: 100vw;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  user-select: none;
  .cover{
    width: 100vw;
    height: 100vh;
    background-color: #fff;
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: center;
    .lyric{
      text-align: center;
      position: absolute;
      top: 15px;
    }
    .start{
      width: 80px;
      height: 30px;
      line-height: 30px;
      border-radius: 10px;
      border: 1px solid;
      text-align: center;
    }
  }
  .txt-right{
    position: absolute;
    right: 20px;
    color: #aaa;
    .txt{
      margin-bottom: 10px;
    }
    .txt-active{
      color: #ff0;
    }
    .clear{
      color: #aaa;
      padding-top: 10px;
      border-top: 1px dashed;
    }
  }
  .count{
    position: absolute;
    top: 15px;
    font-size: 28px;
    text-align: center;
    color: #fff;
  }
  .img{
    width: 47vw;
    height: 35vw;
  }
  .img-active{
    animation: muyuScale 300ms;
  }
  .tips{
    position: absolute;
    color: #fff;
    top: 20%;
    right: 25%;
    opacity: 0;
  }
  .tips-active{
    animation: textMove 300ms;
  }
  .aud{
    display: none;
  }
}  
</style>