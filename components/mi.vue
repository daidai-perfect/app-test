<template>
	<div class="mi-container">
		  <div class="header">
			  <div class="center">
				  <div class="left">
					  <span>小米官网</span>｜
					  <span>小米商城</span>｜
					  <span>MIUI</span>｜
					  <span>loT</span>｜
					  <span>云服务</span>｜
					  <span>天星科技</span>｜
					  <span>有品</span>｜
					  <span>小爱开放平台</span>｜
					  <span>企业团购</span>｜
					  <span>资质证照</span>｜
					  <span>协议规则</span>｜
					  <span>下载app</span>｜
					  <span>Select Location</span>
				  </div>
				  <div class="right">
					  <span>登录</span>｜
					  <span>注册</span>｜
					  <span>消息通知</span>
				  </div>
			  </div>
		  </div>
	  </div>
  </template>
	
  <script lang="ts">
  import { defineComponent, ref } from 'vue'
  export default defineComponent({
  setup() {
	  
	  return {
	  
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
  .mi-container{
	  width: 100%;
	  .center{
		  width: 1200px;
		  margin: auto;
	  }
	  .header{
		  width: 100%;
		  height: 26px;
		  background: #333;
		  .center{
			  display: flex;
		  align-items: center;
		  justify-content: space-between;
		  }
		  .left{
			  color:rgba(#fff,0.1);
			  span{
				  color:rgba(#fff,0.5);
				  font-size: 12px;
			  }
		  }
		  .right{
			  color:rgba(#fff,0.1);
			  span{
				  color:rgba(#fff,0.5);
				  font-size: 12px;
			  }
		  }
	  }
  }
  @media screen and (max-width: 750px) {
	  .center{
		  width: 100% !important;
	  }
  }
  </style>
	