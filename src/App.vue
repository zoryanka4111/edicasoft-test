<template>
  <div id="app">
    <!--top BLOCK-->
    <HomeContent/>

    <!--features BLOCK-->
    <Features/>
  </div>
</template>

<script>
import HomeContent from './components/HomeContent.vue'
import Features from './components/Features.vue'

export default {
  name: 'App',
  components: {
    HomeContent,
    Features
  }
}
</script>

<style lang="scss">
/*font Open Sans*/
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@300;400;700&display=swap');

$font-family: 'Open Sans', sans-serif;

*{
  box-sizing: border-box;
}
body{
  margin: 0;
}
#app {
  font-family: $font-family;
  font-size: 16px;
}
</style>
