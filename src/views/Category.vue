<template>
  <div>
    <h1>Category {{ $route.params.category_id }}</h1>
    <products-list :products-list="productsList" />
  </div>
</template>

<script>
  import ProductsList from '../components/ProductsList'

  export default {
    components: {
      ProductsList
    },
    data () {
      return {
        productsList: []
      }
    },
    mounted () {
      fetch('http://localhost:3000/categories/' + this.$route.params.category_id)
        .then((response) => response.json())
        .then((data) => this.productsList = data);
    }
  }
</script>

<style scoped>

</style>
