<template>
  <div id="app">
    
    <HelloWorld/>             <!-- 头部框 -->
    <Tex/>                    <!-- 主要内容框 -->
    <div class="backtop">     <!-- 全局点击返回顶部按钮 -->

    </div>
    
  </div>
</template>

<script >
import HelloWorld from './components/HelloWorld.vue';
import Tex from './components/text.vue';


// 判断滚动实现点击返回顶部和侧边栏2固定
$(document).ready(function(){
  $('.backtop').click(function(){
$(document).scrollTop(0)
  })
 
  $(document).scroll(function(){

    var screen=$(window).width();
    var res=$(this).scrollTop();
    
    if(res>=10){
$('.backtop').css('display','block')
    }else{
$('.backtop').css('display','none')
    }
    console.log(screen);
    if(screen>=800){
    if(res>=337){
      $('.aside2').css({'position':'absolute','top':res-56+'px'})
    }
    else{
      $('.aside2').css({'position':'absolute','left':'766px','top':'283px'})
    }
    }
    else{
      $('.aside2').css({'position':'','left':'','top':''})
    }
  })
})

export default {
  name: 'App',
  
  components: {
    HelloWorld,
    Tex,
   
    
  }
}
</script>

<style>
html{
  width: 100%;
  height: 100%;
  overflow:auto;
  margin:0;
  padding:0;
}
body{
  width: 100%;
  height: 100%;
margin:0;
  padding:0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 100%;
  height: 200%;
  background: #f9f9f9;
  
}
/* 点击返回顶部按钮 */
.backtop{
  position: fixed;
  bottom: 100px;
  right: 10%;
  background: url(./assets/置顶.png) ;
  background-size: 100%;
  width: 40px;
  height: 40px;
  opacity: 0.3;
  z-index: 99;
}
</style>
