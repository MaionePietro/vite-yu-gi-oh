<template lang="">
    <div v-for="n in 20" @click="debug()">
        <div class="card" style="width: 12rem;">
            <img src="..." class="card-img-top" alt="...">
        <div class="card-body">
        <p class="card-text"></p>
  </div>
</div>
    </div>
</template>
<script>
export default {
    props: {
        deskOfCards: {
            Object,
            //required: false
        }
    },
    data() {
        return {

        }
    },
    methods: {
        debug() {
            console.log("test: " + deskOfCards.title )
        }
    }
}
</script>
<style lang="scss" scoped></style>