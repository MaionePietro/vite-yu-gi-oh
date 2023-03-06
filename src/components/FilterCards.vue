<template lang="">
    <div>
        <div class="input-group mb-3">
            <input 
            type="text" class="form-control" placeholder="Inserisci carta" v-model="store.NameCards"
            @keyup.enter="$event => $emit('searchText')"
            >

            <select class="form-select" aria-label="Default select example"
            v-model="store.QuantityOfCards"
            >
              <option selected>Quante carte vuoi pescare</option>
              <option value="20">20</option>
              <option value="50">50</option>
              <option value="100">100</option>
              <option value="200">200</option>
            </select>
        </div>
    </div>
</template>

<script>
import store from '../store';
export default {
    data(){
        return {
            store
            
        }
    }
}
</script>

<style lang="scss" scoped>
    
</style>