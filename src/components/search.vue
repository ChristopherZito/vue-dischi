<template>
<div>
    <select v-model="type" @change="$emit(`genere`, type)">
        <option disabled value="">seleziona un genere</option>
        <option>Rock</option>
        <option>Pop</option>
        <option>Jazz</option>
        <option>Metal</option>
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
  }
}
</script>

<style scoped lang="scss">
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
