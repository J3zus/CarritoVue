<template>
    <div>
        <th scope="row" colspan="2">
            Total de productos
        </th>
        <td>{{totalCantidad}}</td>
        <td>
            <button class="btn btn-danger btn-sm" id="vaciar-carrito" @click="vaciar">
                Vaciar Carrito
            </button>
        </td>
        <td class="font-weight-bold">$ <span>{{ totalPrecio }}</span></td>
    </div>

</template>

<script>

export default{

    methods:{
        vaciar(){
            console.log('vaciar')
            this.$store.commit('vaciarCarrito')
        }
    },

    computed:{
        totalCantidad(){
            //console.log(this.$store.getters.totalCantidad)
            this.$store.getters.totalCantidad
        },
        totalPrecio(){
            this.$store.getters.totalPrecio
        }
    }
}
</script>
