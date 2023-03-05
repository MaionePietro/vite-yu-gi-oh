<script>
import HeadApp from './components/HeadApp.vue';
import MainApp from './components/MainApp.vue';
import Card from './components/CardGame.vue'
export default {
    components:{
        HeadApp,
        MainApp,
        Card
    }
}
</script>

<template>
    <!-- <HeadApp></HeadApp> -->
    <MainApp />
    <!-- <Card></Card> -->
</template>

<style lang="scss" scoped>
@use'./style/general.scss'
</style>
