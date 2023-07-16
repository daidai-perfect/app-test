<template>
  <div class="zhenhuanzhuan">
    <div class="header">
      <div class="center">
        <div class="left">甄嬛传</div>
        <div class="right">
          <div class="item">首页</div>
        </div>
      </div>
    </div>
    <div class="banner">
      <div class="center">
        <!-- <img src="/zhenhuan.png" alt="" class="zhenhuan"> -->
        <!-- <img src="/yongzheng.png" alt="" class="yongzheng"> -->
        <div class="theme-text">
          前端每日一练----甄嬛传
        </div>
        <div class="card">
          <div class="item">
            <p>甄嬛传</p>
            <span>本剧以清朝的雍正帝在位的时期为舞台，以人与人之间的勾心斗角和派系斗争为刻画核心，钜细靡遗的讲述了主角甄嬛如何选秀入宫，一路过关斩将，直到毒杀皇帝并荣昇为圣母皇太后的全过程</span>
          </div>
          <div class="item">
            <p>甄嬛传</p>
            <span>本剧以清朝的雍正帝在位的时期为舞台，以人与人之间的勾心斗角和派系斗争为刻画核心，钜细靡遗的讲述了主角甄嬛如何选秀入宫，一路过关斩将，直到毒杀皇帝并荣昇为圣母皇太后的全过程</span>
          </div>
        </div>
      </div>
    </div>
    <div class="humen">
      <div class="title">人物介绍</div>
      <div class="center">
        <div class="card" v-for="item in humenList" :key="item.id">
          <div class="img-box">
            <img :src=item.url alt="">
          </div>
          <div class="bottom">
            <div class="name">甄嬛|hrejqlhr</div>
            <div class="desc">后宫老大fahufhuewhfwhfhfwhi</div>
          </div>
          <div class="card-hover">
我是甄嬛<br>
我是甄嬛<br>
我是甄嬛<br>
我是甄嬛<br>
我是甄嬛<br>
我是甄嬛<br>
我是甄嬛<br>
          </div>
        </div>
      </div>
    </div>
    <div class="footer">
      <div class="center">
        ©2023/7/15 by 只会写页面的前端小废物
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
export default defineComponent({
  setup() {
    const humenList=[
      {
        id:1,
        name:'雍正',
        desc:'皇上',
        url: "/human1.jpg"
      },
      {
        id:2,
        name:'雍正',
        desc:'皇上',
        url:'/human2.jpg'
      },
      {
        id:3,
        name:'雍正',
        desc:'皇上',
        url:'/human3.jpg'
      },
      {
        id:4,
        name:'雍正',
        desc:'皇上',
        url:'/human4.jpg'
      },
      {
        id:5,
        name:'雍正',
        desc:'皇上',
        url:'/human5.jpg'
      },
      {
        id:6,
        name:'雍正',
        desc:'皇上',
        url:'/human6.jpg'
      },
      {
        id:7,
        name:'雍正',
        desc:'皇上',
        url:'/human7.jpg'
      },
      {
        id:8,
        name:'雍正',
        desc:'皇上',
        url:'/human8.jpg'
      }
    ]
    return {
      humenList
    }
  }
})
</script>
  
<style lang="less" scoped>
@keyframes spin {
  to {
    transform: rotate(1turn);
  }
}
@keyframes animationHover {
  from{
    height: 0;
  }
  to {
    height: 100%;
  }
}
@keyframes typing {
  from { width: 0 }
}
.center {
  width: 1100px;
  margin: auto;
}

.zhenhuanzhuan {
  margin-top: 20px;
  padding-bottom: 100px;
  min-width: 1100px;
  .header {
    .center {
      display: flex;
      justify-content: space-between;
      align-items: center;

      .left {
        width: 80px;
        height: 80px;
        background: #781e0f;
        border-radius: 50%;
        color: #fff;
        line-height: 80px;
        text-align: center;
        font-weight: 500;
        font-size: 16px;
        animation: spin 6s linear infinite;
      }

      .right {
        font-weight: 500;
        font-size: 20px;
      }
    }
  }
  .banner {
    width: 100%;
    height: 600px;
    background: url('../assets/bg1.jpg') top no-repeat;
    background-size: cover;
    margin-top: 180px;
    .center{
      position: relative;
      .zhenhuan{
        position: absolute;
        right: -500px;
        top: 0px;
        width: auto;
        height: 100%;
        z-index: 9999;
      }
      .yongzheng{
        position: absolute;
        right: 500px;
        top: 0px;
        width: auto;
        height: 100%;
      }
      .card {
        width: 460px;
        height: 590px;
        background: rgba(#d38743,0.8);
        position: absolute;
        top: -130px;
        right: 90px;
        .item {
          padding: 0 50px;
          p {
            font-size: 30px;
            font-weight: bold;
            color: #781e0f;
            line-height: 36px;
            margin-top: 85px;
            z-index: 99999;
          }

          span {
            width: 346px;
            font-size: 16px;
            color: #FFFFFF;
            line-height: 24px;
            margin-top: 15px;
          }
        }
      }
      .theme-text{
        position: absolute;
        top: -90px;
        left: 40px;
        font-size: 30px;
        color: #000;
        width: 12em;
        white-space: nowrap;
        overflow: hidden;
        animation: typing 5s steps(12) infinite;
      }
    }
  }
  .humen{
    margin-top: 30px;
    text-align: center;
    .title{
      font-size: 30px;
      margin: 20px;
      font-weight: 500;
    }
    .center{
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
    }
    .card{
      width: 24%;
      margin-right: calc(4% / 3);
      border: 1px solid #781e0f;
      position: relative;
      margin-top: 16px;
      padding: 4px;
      border-radius: 20px;
      cursor: pointer;
      &:nth-child(4n){
        margin-right: 0;
      }
      &:hover{
        .card-hover{
          display: block;
          animation: animationHover 1s ;
        }
      }
      .card-hover{
        width: 100%;
        height: 100%;
        position: absolute;
        left: 0;
        bottom: 0;
        background: rgba(#e0852e,0.8);
        display: none;
        overflow: hidden;
        border-radius: 20px;
      }
      .img-box{
        width: 100%;
        height: 300px;
        overflow: hidden;
        border-radius: 50%;
        img{
          width: 100%;
          height: auto;
        }
      }
      .bottom{
        padding: 12px;
        .name{
          font-size: 20px;
          font-weight: 500;
        }
        .desc{
          margin-top: 10px;
          font-size: 14px;
        }
      }
    }
  }
  .footer{
    margin-top: 80px;
    .center{
      border-top: 1px solid #781e0f;
      padding-top: 20px;
      text-align: center;
    }
  }
}
@media screen and (max-width: 750px) {
  .center{
    width: 100% !important;
  }

.zhenhuanzhuan {
  min-width:100%;
}
}
</style>
