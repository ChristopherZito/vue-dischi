<template>
  <div class="disco">
        <div class="img">
            <!-- immagine album -->
            <img :src="element.poster" :alt="element.title">
        </div>
        <h3>
            <!-- Titolo -->
            {{element.title}}
        </h3>
        <span>
            <!-- autore -->
            {{element.author}}
        </span>
        <br>
        <span>
            <!-- anno -->
            {{element.year}}
        </span>
  </div>
</template>

<script>
export default {
  name: 'Album',
  props: {
      element: Object
  }
}
</script>

<style scoped lang="scss">
.disco {
    width: 19%;
    background-color: #2e3a46;
    text-align: center;
    margin-bottom: 20px;
    padding: 20px 20px 50px 20px;
    /* debug */
    /* height: 200px; */
    
    h3 {
        color: #fff;
        margin-bottom: 15px;
    }
    span {
        color: #76787a;
        font-size: 20px;
    }
    .img{
        margin-bottom: 20px;

        img {
            max-width: 100%;
            height: 190.9px;
        }
    }
}
</style>
