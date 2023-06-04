<template>
    <div>
        <div class="nav-style">
            <nav class="navbar bg-dark border-bottom border-bottom-dark" data-bs-theme="dark">
                <div class="container-fluid d-flex justify-content-center">
                    <a class="navbar-brand" href="#">{{tituloNav}}</a>
                </div>
        </nav></div>
        <div class="">
            <div class="alert alert-info mb-0 mt-4 d-flex justify-content-center" role="alert">{{alert1}}</div>
            <div class="alert alert-info d-flex justify-content-center" role="alert">{{alert2}}</div>
        </div>
        <div class="d-flex justify-content-center">
            <table class="table">
                <thead>
                    <tr>
                        <th scope="col">#</th>
                        <th scope="col">{{ titulo1 }} </th>
                        <th class="d-flex justify-content-center" scope="col">{{ titulo2 }} </th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="(game,index) in games" :key="index">
                        <th scope="row">{{index+1}}</th>
                            <td>{{game}}</td>
                            <td class="d-flex justify-content-center"><button class="btn btn-danger" @click="eliminarGame(index)">Eliminar</button></td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>

<script>
export default {
    name: 'component-name',
    props: {
        games:{
            type:Array,
            required:true,
        },
    },
    data: function(){
        return {
            tituloNav:"Tienda Bit-Game",
            titulo1:"Juego",
            titulo2:"Eliminar Juego de tu Lista",
            alert1:"¡Bienvenidos!",
            alert2:"A continuación encontraras la lista de los juegos que prefieres:",

        }
    },
    // computed: {},
    methods: {
        eliminarGame(index){
            this.$emit('eliminarGame', index)
        }

    }
    // watch: {},
    // components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
}
</script>

<style scoped>
    .table{
    border: 2px solid black ;
    margin-top: 30px;
    width: 50%;

}

.navbar{
    height: 40px;
    align-content: center;
}
</style>