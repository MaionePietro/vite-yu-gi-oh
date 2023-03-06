<script>
import CardGame from './CardGame.vue';
import FilterCards from './FilterCards.vue';
import axios from 'axios';
import store from '../store'
export default {
    components: {
        CardGame,
        FilterCards
    },
    data() {
        return {
            store  
        }
    },
    methods: {
        fetchCharacters() {
            const NameCards = this.store.NameCards;
            const QuantityOfCards = this.store.QuantityOfCards;

            axios
                .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&fname=dragon',{
                    params: {
                        fname: NameCards,
                        num: QuantityOfCards,
                    }
                })
                .then((res) => {
                    console.log('chiamata oggetto: '+res.data)
                    this.store.characters = res.data.data
                    console.log('cerca nome: '+ NameCards +'  quantità: '+ QuantityOfCards)
                }).catch((error) => {
                    console.log(error)
                    this.store.characters = []
                    this.store.QuantityOfCards = 0
                })
        },
        search(){
            
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
            <FilterCards @searchText="fetchCharacters"/>
            <div class="container p-5 grid-container">
                <CardGame />
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