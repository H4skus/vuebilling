<template>
  <div id="app">
    <raktar :rows="rows" @raktar-item-changed="Changed" @raktar-item-post="Post" @raktar-item-delete="Delete"/>
  </div>
</template>

<script>
//import Vue from 'vue'
import Raktar from './components/Raktar.vue'
export default {
  name: 'App',
  components: {
    Raktar
  },
  data() {
    return {
      rows: [
        {
          title: 'Kerék',
          price: 100,
          quantity: 12
        },
        {
          title: 'Teleszkóp',
          price: 1000,
          quantity: 300
        },
        {
          title: 'Kormány',
          price: 230,
          quantity: 5
        },
        {
          title: 'Ajtó',
          price: 45120,
          quantity: 321
        },
      ]
    }
  },
  methods:{
      Changed(e) {
      this.rows.map(function (row) {
        if (row.title != e.original.title) {
          return row
        }
        row.title = e.new.title
        return row
      })
    },
    Post(e){
      this.rows.push(e.new)
    },
    Delete(e){
        
          this.rows.splice(this.rows.indexOf(e.original), 1);
        }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>