<template lang="">
    <div v-for="character in store.characters">
        <div class="card text-center" style="width: 12rem;">
            <img :src="deskOfCards.characters.data[n].card_images.image_url" class="card-img-top" alt="carta">
            <div class="card-body">
                <p class="card-text">{{deskOfCards.characters.data[n].name}}</p>
                <p class="card-text">{{deskOfCards.characters.data[n].archetype}}</p>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        CardsStore: {
            Object,
            required: false
        }
    },
    data() {
        return {
            
        }
    }
}
</script>
<style lang="scss" scoped></style>