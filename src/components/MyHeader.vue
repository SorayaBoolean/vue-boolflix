<template>
  <div>
    <input v-model="textSearched " placeholder="Cerca" type="text">
    <button @click="$emit('search', textSearched )">Cerca</button>
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

</style>