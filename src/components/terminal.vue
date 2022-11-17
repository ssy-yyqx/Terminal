<template>
  <div id="app">
    <terminal name="my-terminal" @execCmd="onExecCmd" :show-header="false" :show-log-time="false" :context.sync="context"></terminal>
  </div>
</template>

<script>
import Terminal from "vue-web-terminal"

export default {
  name: 'App',
  components:{Terminal},
  data(){
    return {
      context: 'redis:0'
    }
  },
  methods: {
    onExecCmd(key, command, success, failed) {
      let allClass = ['success', 'error', 'system', 'info', 'warning'];

      let clazz = allClass[Math.floor(Math.random() * allClass.length)];
      success({
        type: 'normal',
        class: clazz,
        tag: '成功',
        content: '123'
      })
    }
  }
}
</script>

<style>
body, html, #app {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
}
.terminal-window{
  text-align: left;
}
</style>
