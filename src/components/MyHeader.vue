<template>
  <div class="header">
    <h3>BOOTFLIX</h3>
    <div class="input_container">
      <input v-model="textSearched " placeholder="Cerca" type="text">
      <button @click="$emit('search', textSearched )">Cerca</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MyHeader',
  data () {
    return {
      textSearched: ''
    }
  }
}
</script>

<style scoped lang="scss">
  .header{
    width: 100vw;
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 80px;
    background-color: black;

     h3{
      color:red;
      margin-left: 20px;
     }
     .input_container {
      margin-right: 20px;
     }
  }
</style>