<template>
  <div class="product">
    <div class="product-image"></div>
    <div class="product-info">
      <h1>{{ product }}</h1>
      <p>{{ description }}</p>
    </div>
  </div>

</template>

<script>
  export default {
    name: 'App',
    components: {
    },
    data() {
      return {
        product: 'Socks',
        description: 'A pair of warm fuzzy socks',
        image: 'https://www.vuemastery.com/images/challenges/vmSocks-green-onWhite.jpg',
      };
    },
  };

</script>


<style scoped>
  body {
    font-family: tahoma;
    color: #282828;
    margin: 0px;
  }

  .product {
    display: flex;
  }

  img {
    border: 1px solid #d8d8d8;
    width: 70%;
    margin: 40px;
    box-shadow: 0px .5px 1px #d8d8d8;
  }

  .product-image {
    flex-basis: 700px;
  }

  .product-info {
    margin-top: 10px;
    flex-basis: 500px;
  }

</style>
