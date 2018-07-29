<template>
  <div id="app">
    <div class="wrapper">
      <Card v-for="thing in products" :key="thing.id" :msg="thing"/>
    </div>
  </div>
</template>

<script>
    import Card from './components/Card.vue'

    export default {
        name: 'app',
        components: {
            Card
        },
        data() {
            return {
                stuff: []
            }
        },
        mounted() {
            this.$nextTick(() => {
                this.axios
                    .get('https://api.myjson.com/bins/13catm')
                    .then((response) => {
                        this.stuff = response.data;
                    });
            });
        },
        computed: {
            products() {
                let products = this.stuff.sort((a, b) => {
                    return a.price - b.price;
                });
                return products;
            }
        }
    }
</script>

<style>
  body {
    background-color: pink;
  }
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
  .wrapper {
    margin: 0 5vw;
    display: flex;
    flex-wrap: wrap;
    width: 90vw;
  }
</style>
