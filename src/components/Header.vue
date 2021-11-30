<template>
  <div id="container">
      <div>
        <i class="fab fa-spotify"></i>
      </div>
      <div id="ricerca">
        <Search @genere="searchType"/>
        <SearchArtist :artisti="inputArr" @authors="searchAuthors"/>
    </div>
  </div>
</template>

<script>

import Search from '@/components/search.vue'
import SearchArtist from '@/components/SearchArtist.vue'

export default {
  name: 'Header',
  components: {
    Search,
    SearchArtist
  },
  props: {
    inputArr: Array,
  },
  data() {
    return {
      authorToSearch:"",
      albumToSearch:"",
    }
  },
  methods: {
    searchAuthors(author){
      this.authorToSearch = author;
      this.$emit(`authorSearched`,this.authorToSearch)
    },
    searchType(album){
      this.albumToSearch = album;
      this.$emit(`albumSearched`,this.albumToSearch)
    }
  }
}
</script>

<style scoped lang="scss">
#container {
  width: 100%;
  background-color: #2e3a46;
  padding: 10px 30px;
  /* debug */
  /* height: 100px; */

  div {
     /*  width: 100px; */
      /* debug */
      /* height: 100px; */
      /* background-color: #1ed05d; */

      i {
          color: green !important;
          font-size: 50px;
      }
  }

  #ricerca {
  width: 60%;
  margin: auto;
  padding: 10px;
}
}
</style>
