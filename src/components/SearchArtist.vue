<template>
<div>
    <select v-model="author" @change="$emit(`authors`, author)">
        <option disabled value="">Seleziona un artista</option>
        <option 
        v-for="artist, i in artisti"  :key="i">
        {{artist.author}}
        </option>
    </select>
    <button @click="reset">
        Reset search artist
    </button>
</div>
</template>

<script>
export default {
    name: 'SearchArtist',
    data() {
        return {
            author: "",
        }
    },
    props: {
        artisti: Array
    },
    methods: {
        reset() {
            this.author = "";
            this.$emit(`authors`, this.author)
        }
    }
}
</script>

<style scoped lang="scss">
div {
    display: flex;
}
select {
    padding: 10px;
    background-color: purple;
    color: #fff;
}
button {
    padding: 10px;
    margin-left: 20px;
    background-color: purple;
    color: #fff;
}
</style>
