<template lang="pug">
  #app
    Header(v-model="search")
</template>

<script>
import Header from './components/Header/Header'

export default {
  name: 'App',
  components: {
    Header
  },
  data () {
    return {
      search: ''
    }
  }
}
</script>

<style lang="sass">
body
  background: linear-gradient(135deg, #83458e 0%,#608dc9 100%)
#app
  text-align: center
</style>
