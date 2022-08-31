<template>
  <div id="app">
    <MyHeader @search="searching"/>
    <MyMain />
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MyMain from './components/MyMain.vue'


export default {
  name: 'App',
  components: {
    MyMain,
    MyHeader,
},
methods: {
  searching (searchedText) {

}
}
 
}
</script>

<style lang="scss">

</style>
