<script>
import CardGame from './CardGame.vue';
import axios from 'axios';
import store from '../store'
export default {
    components: {
        CardGame
    },
    data() {
        return {
            store
            
        }
    },
    methods: {
        fetchCharacters() {
            axios
                .get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
                .then((res) => {
                    console.log(res.data.data.name)
                    this.store.characters = res.data
                    //console.log("store: "+this.store.characters.data[0].card_images.image_url)
                })
        }
    },
    created() {
        this.fetchCharacters()
    }
}
</script>

<template lang="">
    <div class="box-orange">
        <div class="container p-4">
            <div class="dropdown">
                <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown" aria-expanded="false">
                  Dropdown button
                </button>
                <ul class="dropdown-menu">
                    <li><a class="dropdown-item" href="#">Action</a></li>
                    <li><a class="dropdown-item" href="#">Another action</a></li>
                    <li><a class="dropdown-item" href="#">Something else here</a></li>
                </ul>
            </div>
            <div class="container p-5 grid-container">
                <CardGame :deskOfCards="store" />
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.box-orange{
    background-color: orange;
}
.grid-container{
    background-color: white;
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 10px;
}
</style>