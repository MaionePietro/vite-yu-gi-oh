<template lang="">
    <div v-for="character in store.characters">
        <div class="card text-center box-orange" style="width: 12rem;">
            <img :src="character.card_images[0].image_url" class="card-img-top" alt="carta">
            <div class="card-body">
                <p class="card-text">{{character.name}}</p>
                <p class="card-text">{{character.archetype}}</p>
            </div>
        </div>
    </div>
</template>
<script>
import store from '../store'
export default {
    data() {
        return {
            store
        }
    }
}
</script>
<style lang="scss" scoped>
.box-orange{
    background-color: orange;
}
</style>