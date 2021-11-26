<template>
  <div id="container">
      <div>
        <i class="fab fa-spotify"></i>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
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
        width: 100px;
        /* debug */
        /* height: 100px; */
        /* background-color: #1ed05d; */

        i {
            color: green !important;
            font-size: 50px;
        }
    }
}
</style>
