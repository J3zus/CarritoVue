<template>
  <div class="container">
    <h1 class="text-center">Carrito + VUE + Vanilla</h1>
    <hr>
    <Carrito />
    <div class="row">
      <Card v-for="producto in productos" :key="producto.id"
            :producto="producto"
      />
    </div>
  </div>
</template>

<script>
import Card from '@/components/Card.vue'
import Carrito from '@/components/Carrito.vue'
//import { useStore } from 'vuex'

export default {
  name: 'App',
  components: {
    Card,
    Carrito
  },
  mounted() {
      this.$store.dispatch('fetchData')
      //const productos = computed( () => store.state.productos )
  },
  computed: {
    productos(){
      return this.$store.state.productos
    },
    carrito(){
      return this.$store.state.carrito
    }
  },
  watch: {
    productos(){
      //console.log('Cambia Valor, this.$store.state.productos')
    },
    carrito(){

    }
  },
  data () {
    return {

    }
  },
};
</script>