<template>
  <div class="home">
    <h1>Homepage</h1>
    <p>
      <router-link :to="{name: 'categories'}">Go to categories page</router-link>
    </p>
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
      fetch('http://localhost:3000/highlighted/')
        .then((response) => response.json())
        .then((data) => this.productsList = data);
    }
  }</script>
