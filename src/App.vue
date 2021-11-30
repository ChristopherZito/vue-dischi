<template>
<section>
  <header>
    <Header
    :inputArr="authorArr"
    :inpurGenre="inGenre"
    @authorSearched="autorReturn"
    @albumSearched="albumReturn"/>
  </header>
  <main>
    <Mainbody
    @datiArr="selectArr"
    @albumsArr="genreArr"
    :authorIn="authorBack"
    :albumIn="albumBack"/>
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
  },
  data(){
    return {
      authorArr:[],
      authorBack:"",
      albumBack:"",
      inGenre: [],
    }
  },
  methods: {
    selectArr(outArr){
      this.authorArr = outArr;
    },
    genreArr(genre){
      this.inGenre = genre;
    },
    autorReturn(dato){
      this.authorBack = dato;
      /* console.log(this.authorBack); */
    },
    albumReturn(dato){
      this.albumBack = dato;
      /* console.log(this.albumBack); */
    }
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
  height: 93vh;
  /* debug */
  /* height: 500px; */
}
</style>
