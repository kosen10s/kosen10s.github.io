<template lang='pug'>
include ../../pug-mixins/retina-img
#xs-activity-list.container
  h2 活動内容
  .activity-wrapper(v-for='(content, index) in activity_list')
    .columns.is-desktop(v-if="index == 0 || index % 3 == 0")
      .column
        xs-activity(:title='activity_list[index].title'
          :description='activity_list[index].description'
          :img='activity_list[index].img')
      .column
        xs-activity(v-if="activity_list.length > index+1"
          :title='activity_list[index+1].title'
          :description='activity_list[index+1].description'
          :img='activity_list[index+1].img')
      .column
        xs-activity(v-if="activity_list.length > index+2"
          :title='activity_list[index+2].title'
          :description='activity_list[index+2].description'
          :img='activity_list[index+2].img')
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
        },
        {
          title: 'おしゃれスポーツ部',
          img: require('../../assets/images/activity_oshaspo.png'),
          description: 'ダーツとビリヤードをして、ついでに飲みます。月に一度を目処に活動をしています。'
        },
        {
          title: 'Advent Calendar',
          img: require('../../assets/images/activity_advent_calendar.png'),
          description: '年に一回、12月に毎日1記事ずつkosen10sメンバーがブログを書きます。2017年12月もやってます。'
        },
        {
          title: '麻雀部',
          img: require('../../assets/images/activity_mahjong.png'),
          description: '麻雀をたしなみます。初心者大歓迎で実際に初心者も参加している部活です。'
        },
        {
          title: 'バドミントン',
          img: require('../../assets/images/activity_badminton.png'),
          description: 'バドミントンをします。初心者大歓迎です。体育館が取れて、気が向いたら開催されます。'
        },
        {
          title: 'ボドゲ',
          img: require('../../assets/images/activity_boardgame.png'),
          description: 'ボードゲームと謎解き・リアル脱出ゲームをやっています。'
        },
        {
          title: '飲み会・食す会',
          img: require('../../assets/images/activity_add.png'),
          description: 'kosen10sのSlackにJoinして雑にゆる募すると同士が見つかるかもしれません！',
          has_button: true,
          is_red: true
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
  .columns {
    flex-wrap: wrap;
    margin-bottom: 1.5rem;
  }
}
</style>
