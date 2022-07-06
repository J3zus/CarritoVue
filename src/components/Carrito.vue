<template>
    <div class="my-5">
        <h4 class="text-center">My carrito</h4>
        <table class="table">
            <thead>
                <tr>
                    <th scope="col">#</th>
                    <th scope="col">Item</th>
                    <th scope="col">Cantidad</th>
                    <th scope="col">Accion</th>
                    <th scope="col">Total</th>
                </tr>
            </thead>
            <tbody id="items">
                <Item v-for="item in carrito" :key="item.id" :item="item"/>
            </tbody>
            <tfoot>
                <tr id="footer-carrito">
                    <th scope="row" colspan="5" v-if="Object.keys(item).length === 0">Carrito Vacio - Compra ya !!!</th>
                    <Footer v-else/>
                </tr>
            </tfoot>
        </table>
    </div>
</template>

<script>
import Item from "./Item.vue"
import Footer from './Footer.vue'

export default {

    data: () => ({

    }),
    components:{
        Item,
        Footer
    },
    computed:{
        carrito(){
            console.log('computed', this.$store.state.carrito)
            return this.$store.state.carrito
        } 
    },
    watch:{
        
        /*carrito(){
            console.log('watch', this.$store.state.carrito)
            return this.$store.state.carrito

        }*/
    }
}
</script>