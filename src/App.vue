<template>
  <lay-fullscreen :target="elRef" v-slot="{ enter, exit, toggle, isFullscreen }" @fullscreenchange=fullscreen2>
    <div ref="elRef" class="wrapper-fullscreen">
      <lay-button type="normal" @click="enter()">进入全屏</lay-button>  
      <lay-button type="normal" @click="exit()">退出</lay-button> 
      <lay-button type="warm" @click="toggle()"> 切换: {{isFullscreen ? "退出" : "进入全屏"}} </lay-button>
    </div>
  </lay-fullscreen>
</template>

<script>
import { ref } from 'vue'

export default {
  setup() {
    const elRef = ref(null);
    const fullscreen2 = function(isFullscreen){
      console.log(isFullscreen)
    }
    return {
      elRef,
      fullscreen2
    }
  }
}
</script>
<style>
.wrapper-fullscreen{
  padding:10px;
  border:1px solid #dddddd;
  background-color:#F6F6F6;
  display:inline-block
}
</style>
