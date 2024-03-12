<template>
  <div id="app">
    <div v-for="(item,index) in ProductList" :key="index">
      <p>{{item.name}}</p>
      <p>{{item.price}}</p>
      <p>{{item.reviews[1].rating}}</p>
    </div>


  </div>

</template>

<script>
  export default {
    data () {
      return {
        ProductList: [
          {
            name: "Product 1", 
            price: 99.99, 
            reviews: [{ id: 1 }, { rating: 4 }, { comment: "Great product!" }]
          }]
      }
    }
  }
</script>