<script setup>
import HelloWorld from './components/HelloWorld.vue'

import Sidebar from "./components/Sidebar.vue";
import Home from "./Views/Home.vue";</script>

<template>
<!--  总-->
  <div id="Body">
    <span style="--wails-draggable:drag" id="title"></span>
    <Sidebar />
    <home/>
  </div>
</template>

<style lang="scss" scoped>
#title{
  position: absolute;
  width: 100vw;
  height: 40px;
  border-radius: 20px 20px 0 0;
  top: 0;
  left: 0;
}
#Body{
  display: flex;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
  background: white;
  border-radius: 20px;
}
</style>