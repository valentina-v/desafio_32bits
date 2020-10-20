<template>
    <div>
        <h2>Stock total disponible: {{totalStock}}</h2>
        <list :games="availableGames"></list>
        <h2>Busca tu juego</h2>
        <input type="text" v-model="searchId" >
        <ul>
            <li v-for="game in searchGamesById" :key="game.id">{{game.id}} | {{game.name}} | {{game.stock}} | {{game.price}} </li>
        </ul>
    </div>
</template>

<script>

import { mapGetters } from 'vuex'

import List from '@/components/List'
export default {
    data() {
        return {
            searchId: ""
        }
    },
    components: {
        List
    },
    computed: {
        ...mapGetters(["availableGames", "searchById", "totalStock"]),
        searchGamesById() {
            return this.searchById(this.searchId)
        },
    },

}
</script>

<style>

</style>