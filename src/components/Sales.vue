<template>
    <div>
       <p> Existen {{ availableGames.length }} en stock</p>
       <list 
       :hasButton="true" 
       :games="availableGames" 
       @sell-product="saleProduct"> </list>
    </div>
</template>

<script>

import {mapGetters, mapActions} from 'vuex'
import List from "@/components/List";
export default {
    components: {
        List
    },
    computed: {
    ...mapGetters (["availableGames"])
    },
    methods: {
        ...mapActions (["processSale"]),
        saleProduct(payload) {
            this.processSale(payload.game);
        },
    },
}
</script>


<style>

</style>