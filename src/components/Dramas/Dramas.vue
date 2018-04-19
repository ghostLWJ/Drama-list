<template lang='pug'>
  .dramas
    .drama(v-for="drama in dramas")
      .header(:style="bg_css(drama.vertical_poster)")
      .content
        .year {{ drama.year }}
        .info
          .watch
            span.icon-eye
            .views {{ drama.total_views }}
          .eps {{ drama.total_eps }}
        h3.name {{ drama.name }}

</template>

<script>
export default {
  methods: {
    bg_css (url) {
      return { 'background-image': `url(${url})`}
    }
  },
  props: {
    dramas: {
      type: Array,
      default: []
    }
  }
}
</script>


<style lang='sass' scoped>
@import url("../../common/styles/icon.css")
.dramas
  padding-top: 15px
  display: flex
  justify-content: center
  align-items: center
  > .drama
    flex: 0 0 200px
    margin-right: 13px
    padding: 3px
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.3)
    box-sizing: border-box
    &:hover
      > .header
        background-size: 90%
    > .header
      height: 225px
      background-size: 100%
      background-repeat: no-repeat
      background-position: center center
      transition: .5s
.dramas > .drama > .content
  display: flex
  flex-direction: column
  padding: 3px 0 0 0
  letter-spacing: .05em
  > .year
    text-align: left
    &:after
      display: inline-block
      content: '年'
      margin-left: 3px
      font-size: .85rem
  > .info
    display: flex
    flex-direction: row
    justify-content: space-between
    padding-top: 3px
    > .watch
      display: flex
      > span.icon-eye
        color: #CDCDCC
      > .views
        margin-left: 7px
    > .eps
      &:before, &:after
        display: inline-block
        font-size: .85rem
      &:before
        content: '共'
        margin-right: 3px
      &:after
        content: '集'
        margin-left: 3px
  > .name
    padding-top: 13px
    padding-bottom: 13px
    letter-spacing: .07em
    font-size: 1.2rem
</style>
