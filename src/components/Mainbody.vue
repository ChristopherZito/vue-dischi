<template>
<section>
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


export default {
    name: 'Mainbody',
    components: {
        Album,
},
data(){
    return {
        loading: false,
        albums: [],
        urlDisk:"https://flynn.boolean.careers/exercises/api/array/music",
    }
},
props: {
    authorIn: String,
    albumIn: String,
},
created() {
    this.subElement();
},
computed:{
    newAlbum() {
        if(this.albumIn == "" && this.authorIn == ""){
            return this.albums;
        }
        return this.albums.filter((tipo) => {
            if(this.albumIn != "" && this.authorIn == ""){
                return tipo.genre.toLowerCase().includes(this.albumIn.toLowerCase())
            }else if (this.albumIn == "" && this.authorIn != ""){
                return tipo.author.toLowerCase().includes(this.authorIn.toLowerCase())
            }   
        })   
        
    }
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
            this.$emit(`datiArr`, this.albums)
            /* console.log(this.loading , "&" ,this.albums); */
        })
    },
}
}
</script>

<style scoped lang="scss">


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
