<template lang='pug'>
include ../../pug-mixins/retina-img
#xs-activity-list.container
  h2 活動内容
  .columns.is-desktop
    xs-activity(v-for='(content, key) in activity_list'
      :class='content.class_name'
      :title='content.title'
      :description='content.description'
      :img='content.img')
</template>

<script>
import Vue from 'vue'
import XsActivity from './XsActivity'

export default {
  name: 'XsActivityList',
  data () {
    return {
      activity_list: [
        {
          title: 'Chat on Slack',
          img: require('../../assets/images/activity_slack.png'),
          description: 'たくさんの話題が上がります。テック系から愚痴・相談、オタクコンテンツの共有までさまざまです。'
        },
        {
          title: 'kosen10s LT',
          img: require('../../assets/images/activity_lt.png'),
          description: 'kosen10sのみんなでLT会をします。エモ・テック・おもしろ・オタクコンテンツ、何でもあり。'
        },
        {
          title: '飲み会・食す会',
          img: require('../../assets/images/activity_party.png'),
          description: '東京のメンバーを中心に暇な時に雑に飲み会をします。新年会や秋吉、カレーメシを食す会が主です。'
        }
      ]
    }
  }
}

Vue.component('xs-activity', XsActivity)
</script>

<!-- Add 'scoped' attribute to limit CSS to this component only -->
<style scoped lang='scss'>
@import '../../assets/sass/mixins';

#xs-activity-list {
  h2 {
    @include section-title;
  }
  margin-top: 5rem;
  margin-bottom: 5rem;
}
</style>
