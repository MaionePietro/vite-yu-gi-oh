<script>
import axios from 'axios';
import store from '../store'
export default {
    data(){
        return{
            store
        }
    },
    methods:{
        fetchCharacters(){
            axios
            .get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
            .then((res)=>{
                console.log(res)
                this.store.characters = res.data.name
            })
        }
    },
    created(){
        this.fetchCharacters()
    }
}
</script>

<template lang="">
    <div>
        
    </div>
</template>

<style lang="scss">
    
</style>