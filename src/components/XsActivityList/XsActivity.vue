<template lang="pug">
include ../../pug-mixins/retina-img
#xs-activity
  img(:src="img")
  .contents
    h3.header
      span.title {{ title }}
    p.description {{ description }}
</template>

<script>
export default {
  name: 'XsActivity',
  props: ['title', 'img', 'description'],
  data () {
    return {
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../../assets/sass/mixins';
#xs-activity {
  background-color: white;
  border-radius: 5px;
  margin: 0 0.25rem 1.25rem;
  padding: 0;
  height: 100%;
  box-shadow: 0px 7px 10px 10px rgba($navy, 0.04);
  img {
    display: block;
    width: 100%;
    border-radius: 5px 5px 0 0;
  }
  .contents {
    padding: 1rem 2rem 2.5rem;
    .header {
      display: flex;
      .title {
        display: inline-block;
        font-size: 1.75rem;
        color: $navy;
        flex-grow: 1;
        line-height: 2.75rem;
        margin-bottom: 1.0rem;
      }
    }
    .description {
      font-size: 1.1rem;
    }
  }
}
</style>
