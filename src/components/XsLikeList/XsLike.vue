<template lang="pug">
include ../../pug-mixins/retina-img
#xs-like(v-bind:class="[class_name, 'column']")
  h3.header
    img(:src="img")
    span.title {{ title }}
  p.description {{ description }}
</template>

<script>
export default {
  name: 'XsLike',
  props: ['title', 'img', 'class_name', 'description'],
  data () {
    return {
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../../assets/sass/mixins';
@mixin xs-like-with-color($key-color) {
  background-color: white;
  border-radius: 5px;
  padding: 2rem 2rem;
  margin: 1.25rem;
  box-shadow: 0px 11px 10px 10px rgba($key-color, 0.08);
  .header {
    display: flex;
    img {
      display: inline-block;
    }
    .title {
      display: inline-block;
      font-size: 1.5rem;
      color: $key-color;
      margin-left: 0.75rem;
      flex-grow: 1;
      line-height: 65px;
    }
  }
  .description {
    font-size: 1.1rem;
    margin-top: 1.25rem;
  }
}

#xs-like.red {
  @include xs-like-with-color($red);
}

#xs-like.blue {
  @include xs-like-with-color($blue);
}

#xs-like.green {
  @include xs-like-with-color($green);
}
</style>
