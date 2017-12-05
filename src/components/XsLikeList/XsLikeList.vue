<template lang='pug'>
include ../../pug-mixins/retina-img
#xs-like-list.container
  h2 kosen10sの大切にする3つの「すき」
  .columns.is-desktop
    xs-like(v-for='content in like_list'
      :class='content.class_name'
      :title='content.title'
      :description='content.description'
      :img='content.img')
</template>

<script>
import Vue from 'vue'
import XsLike from './XsLike'

export default {
  name: 'XsLikeList',
  data () {
    return {
      like_list: [
        {
          title: 'Tech',
          class_name: 'blue',
          img: require('../../assets/images/like_tech.png'),
          description: 'テクノロジーとテクニック。工業技術はもちろん、話術・交渉術なども含めて大切にしています。'
        },
        {
          title: 'わいわい',
          class_name: 'red',
          img: require('../../assets/images/like_yy.png'),
          description: '同い年・高専卒という共通項の多さからどんな話題も自然に盛り上がる雰囲気が出来ています。'
        },
        {
          title: 'ぶっちゃけ',
          class_name: 'green',
          img: require('../../assets/images/like_pure.png'),
          description: '境遇が似ている人同士だからこそ、お互いのありのままの発言を広く認めています。'
        }
      ]
    }
  }
}

Vue.component('xs-like', XsLike)
</script>

<!-- Add 'scoped' attribute to limit CSS to this component only -->
<style scoped lang='scss'>
@import '../../assets/sass/mixins';

#xs-like-list {
  h2 {
    @include section-title;
  }
  margin-top: 5rem;
  margin-bottom: 5rem;
}
</style>
