<template>
  <div id="app">
    <header>
      <div id="logo">
        <router-link :to="{name: 'home'}">Vue E-shop</router-link>
      </div>
      <the-cart />
    </header>

    <main>

      <router-view />

    </main>

    <footer>
      <div id="usefulLinks">
        <a href="#">Send us feedback</a>
      </div>
      <div id="copyright">
        &copy; 2019 by Fczbkk
      </div>
    </footer>
  </div>
</template>

<script>
  import TheCart from './components/TheCart'
  export default {
    components: {
      TheCart
    }
  }
</script>

<style>
  body {
    background: #C0C0C0;
    color: #333;
    font-family: helvetica, arial, sans-serif;
    padding: 0;
    margin: 0;
  }

  a {
    color: #FF6700;
  }

  header, main, footer {
    padding: 2em;
  }

  header, footer {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }

  header {
    background: #004E98;
    color: #fff;
  }

  header div {
    font-weight: bold;
    font-size: 1.25em;
  }

  header a {
    text-decoration: none;
    color: #EBEBEB;
  }

  main {
    background: #EBEBEB;
  }

  .productsList {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    grid-column-gap: 1em;
    grid-row-gap: 1em;
  }

  .productDetail {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: flex-start;
  }

  .productDetail .details {
    flex-grow: 1;
  }

  .productDetail .image {
    margin-left: 2em;
  }

  .productDetail .image img {
    width: 100%;
    max-width: 500px;
  }

  .box {
    border: 2px solid #3A6EA5;
  }

  .box .title {
    background: #3A6EA5;
    color: #EBEBEB;
  }

  .box .title h3 {
    margin: 0;
    font-size: 1em;
  }

  .box .title, .box .content {
    padding: 1em;
  }

  .soldOut {
    display: inline-block;
    font-weight: bold;
    background: #FF6700;
    color: #EBEBEB;
    padding: 0.5em 1em;
    transform: rotate(-15deg);
    transform-origin: center center;
  }

  .tabs {
    border-bottom: 2px solid #3A6EA5;
  }

  .tabs button {
    font-weight: bold;
    border: 2px solid #3A6EA5;
    border-bottom: none;
    padding: 0.5em 2em;
    background: #C0C0C0;
  }

  .tabs button:hover {
    background: #FF6700;
  }

  .tabs button.active {
    background: #3A6EA5;
    color: #EBEBEB;
  }

  .addToCart button, .addToCart input {
    font-weight: bold;
    padding: 0.5em 1em;
    border: 2px solid #004E98;
  }

  .addToCart input {
    text-align: right;
    background: #EBEBEB;
  }

  .addToCart button {
    background: #3A6EA5;
    color: #EBEBEB;
  }

  .addToCart button:hover {
    background: #FF6700;
  }

  .price {
    font-size: 2em;
    font-weight: bold;
    padding: 0.25em;
  }

</style>
