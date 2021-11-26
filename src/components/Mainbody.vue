<template>
  <div id="container">
        <div id="load" v-if="loading === false">
            Loading...
        </div>
        <Album 
        v-else
        v-for="album, i in albums" :key="i"
        :element="album"/>
  </div>
</template>

<script>
import axios from "axios"
import Album from '@/components/Album.vue'

export default {
  name: 'Mainbody',
  components: {
    Album
  },
  data(){
      return {
          loading: false,
          albums: [],
          urlDisk:"https://flynn.boolean.careers/exercises/api/array/music",
      }
  },
  created() {
      this.subElement();
  },
  methods: {
      subElement() {
          axios
          .get(this.urlDisk)
          .then((block) => {
              /* console.log(block.data.response); */
              /* console.log(this.loading , "&" ,this.albums); */
              this.albums = block.data.response;
              this.loading = true;
              /* console.log(this.loading , "&" ,this.albums); */
          })
      }
  }
}
</script>

<style scoped lang="scss">
#container {
    width: 60%;
    margin: 0 auto;
    padding: 50px 0;

    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;

    #load{
        color: #fff;
        margin: auto;
    }
}
</style>
