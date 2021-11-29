<template>
<div>
    <select v-model="type" @change="$emit(`genere`, type)">
        <option disabled value="">select one genre</option>
        <option>Rock</option>
        <option>Pop</option>
        <option>Jazz</option>
        <option>Metal</option>
    </select>
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
}
</script>

<style scoped lang="scss">

</style>
