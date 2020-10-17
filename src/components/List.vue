<template>
  <div>
    <ul>
         <li v-for="game in games" :key="game.id" :style="{backgroundColor: game.color}">{{game.id}} | {{game.name}} | {{game.stock}} | {{game.price}} </li>
    </ul>
  </div>
</template>

<script>
export default {
    props: ["games"]

}
</script>

<style>

</style>