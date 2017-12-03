<template lang="pug">
  #index
    xs-header
    //- xs-like-list
    //- xs-activity-list
    //- xs-cta
    //- xs-footer
</template>

<script>
import Vue from 'vue'
import XsHeader from './XsHeader/XsHeader'

export default {
  name: 'Index',
  data () {
    return {
      msg: '2010年に高専入学した人のコミュニティ'
    }
  }
}

Vue.component('xs-header', XsHeader)
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
