<template>
<div>
    <select v-model="type" @change="$emit(`genere`, type)">
        <option disabled value="">seleziona un genere</option>
        <option 
        v-for="genre, i in generi" :key="i"
        >{{genre}}</option>
    </select>
    <button @click="reset">
        Reset search genre
    </button>
</div>
</template>

<script>
export default {
    name: 'Search',
    data() {
        return {
            type: "",
        }
    },
    methods: {
        reset() {
            this.type = "";
            this.$emit(`genere`, this.type)
        }
    },
    props: {
        generi: Array,
    }
}
</script>

<style scoped lang="scss">
div {
    display: flex;
    margin-bottom: 10px;
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
    margin-bottom: 10px;
}
</style>
