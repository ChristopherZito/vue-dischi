<template>
<section>
    <div id="ricerca">
        <Search @genere="searchType"/>
    </div>
    <div id="container">
        <div id="load" v-if="loading === false">
            Loading...
        </div>
        <Album 
        v-else
        v-for="album, i in newAlbum" :key="i"
        :element="album"/>
    </div>
</section>
</template>

<script>
import axios from "axios"
import Album from '@/components/Album.vue'
import Search from '@/components/search.vue'

export default {
    name: 'Mainbody',
    components: {
        Album,
        Search
},
data(){
    return {
        searchText:"",
        loading: false,
        albums: [],
        urlDisk:"https://flynn.boolean.careers/exercises/api/array/music",
    }
},
created() {
    this.subElement();
},
computed:{
    newAlbum() {
        if(this.searchText == ""){
            return this.albums;
        }
        return this.albums.filter((tipo) => {
            return tipo.genre.toLowerCase().includes(this.searchText.toLowerCase())
        })   
    }
},
methods: {
    searchType(style){
        this.searchText = style;

    },
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
    },
}
}
</script>

<style scoped lang="scss">
#ricerca {
    width: 60%;
    margin: auto;
    padding: 10px;
}

#container {
    width: 60%;
    margin: 0 auto;
    padding: 50px 0 0;

    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;

    #load{
        color: #fff;
        margin: auto;
    }
}
</style>
