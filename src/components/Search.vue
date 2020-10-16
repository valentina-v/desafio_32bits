<template>
    <div>
        <h2>Busca tu juego</h2>
        <input type="text" v-model="searchId" >
        <ul>
            <li v-for="game in searchByIdGames" :key="game.id">{{game.id}} | {{game.name}} | {{game.stock}} | {{game.price}} </li>
        </ul>
    </div>
</template>

<script>
import { mapGetters, mapState } from 'vuex'
export default {
    data() {
        return {
            searchId: "",
        }
    }

}
</script>

<style>

</style>