<template lang="pug">
include ../../pug-mixins/retina-img
#xs-header.hero.is-fullheight
  .hero-body
    .container.has-text-centered
      .title
        +retina-img('../../assets/images/header_logo.png')
        p 2010年に高専入学した人のコミュニティ
      .subtitle
        a(href="http://kosen10s-invite.herokuapp.com")
          | JOIN KOSEN10S
</template>

<script>
export default {
  name: 'XsHeader'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$red: #ff585b;
#xs-header {
  background-image: url("../../assets/images/header_bg.jpg");
  background-size: cover;
  background-position: center center;
  .title {
    p {
      font-size: 18px;
      margin-top: 30px;
      color: white;
      font-weight: bold;
    }
  }
  .subtitle {
    margin-top: 160px;
    a {
      &:before {
        content: '';
        display: inline-block;
        background-image: url("../../assets/images/icon_link@3x.png");
        height: 24px;
        width: 24px;
        background-size: contain;
        background-repeat: no-repeat;
        background-position: center center;
        position: relative;
        top: 5px;
        margin: -5px 20px 0 -10px;
      }
      display: inline-block;
      border-radius: 100px;
      background-color: $red;
      padding: 15px 50px;
      color: white;
      box-shadow: rgba($red, 0.3) 0 5px 8px;
      transition: all 0.2s linear;
      box-sizing: border-box;
      border: 2px solid $red;
      &:hover {
        border: 2px solid lighten($red, 10%);
        box-shadow: rgba($red, 0.6) 0 9px 13px;
      }
    }
  }
}
</style>
