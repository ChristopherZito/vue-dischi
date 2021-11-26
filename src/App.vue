<template>
<section>
  <header>
    <Header/>
  </header>
  <main>
    <Mainbody/>
  </main>
</section>
</template>

<script>
import Header from './components/Header.vue'
import Mainbody from './components/Mainbody.vue'

export default {
  name: 'App',
  components: {
    Header,
    Mainbody
  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

main {
  background-color: #1e2d3b;
  /* debug */
  /* height: 500px; */
}
</style>
