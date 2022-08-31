<template>
  <div id="app">
    <MyHeader/>
    <MyMain/>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyMain from './components/MyMain.vue'


export default {
  name: 'App',
  components: {
    MyMain,
    MyHeader
}
}
</script>

<style lang="scss">

</style>
