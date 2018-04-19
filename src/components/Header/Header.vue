<template lang='pug'>
  .header
    .top-wrapper
      .search-wrapper
        span.icon-search
        input.search-bar(type="text" placeholder="搜劇" v-model="search" v-on:input="searchEmit")
</template>

<script>
export default {
  data () {
    return {
      search: ''
    }
  },
  methods: {
    searchEmit: function () {
      this.$emit('input', this.search)
    }
  }
}
</script>


<style lang='sass' scoped>
@import url("../../common/styles/icon.css")
.header
  padding-top: 20px
  > .top-wrapper
    position: relative
    display: flex
    justify-content: center
    align-items: center
    > .search-wrapper
      box-sizing: border-box
      width: 30%
      > span.icon-search
        display: inline-block
        width: 30px
        height: 30px
        line-height: 30px
        text-align: center
        position: absolute
        color: #FFF
      > input.search-bar
        box-sizing: border-box
        width: 100%
        height: 30px
        border-radius: 25px
        padding-left: 30px
        outline: none
        background-color: #CDCDCC
</style>
