<template lang="pug">
  #app
    Header(v-model="search")
    Dramas(:dramas="filterDramas")
</template>

<script>
import Header from './components/Header/Header'
import Dramas from './components/Dramas/Dramas'

export default {
  name: 'App',
  components: {
    Header,
    Dramas
  },
  data () {
    return {
      search: '',
      dramas: []
    }
  },
  created () {
    const that = this;
    this.$axios.get ('/api/dramas')
      .then ( (res) => {
        if (res.status === 200) {
          const dataSource = res.data;
          that.dramas = dataSource.data;
        }
      })
      .catch ( (err) => {
        console.log (err);
      })
  },
  computed: {
    filterDramas () {
      return this.dramas.filter ( (drama) => drama.name.toLowerCase ().includes (this.search.toLowerCase ())
      )
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
