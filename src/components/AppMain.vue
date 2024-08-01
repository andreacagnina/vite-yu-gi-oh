<script>
import AppCard from './AppCard.vue';
import SearchBar from './SearchBar.vue';
import { store } from '../store.js';


export default {
    components: {
        AppCard,
        SearchBar,

    },
    data() {
        return {
            store,
        }
    },
    created(){

    },
    methods:{
        getCardFiltered() {

        }
    },
    computed: {
        filteredCard() {
            if (store.archetypesList){
                return store.CardsArray.filter((elem)=>{
                    return elem.archetype == store.archetypesList
                })
            };
            store.Lunghezza = store.CardsArray.length
            return store.CardsArray;
        }
    }
}
</script>

<template>
    <main>

        <div class="container border_ocre">
            <SearchBar @filter="getCardFiltered()"/>
            <div class="row">
                <div class="col-12">
                    <div class="content ">
                        <div class="col-12">
                            <div class="content bg-dark p-3">
                                <h5 class="text-light">Founds {{filteredCard.length}} cards</h5>
                            </div>
                        </div>
                        <div class="col-12">
                            <div class="row row-cols-2 row-cols-md-3 row-cols-lg-5">
                                <AppCard v-for="card in filteredCard" :key="card.id" :card="card"/>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>

</template>

<style lang="scss" scoped>
@use '../styles/_partials/_bgColor' as *;
.border_ocre {
    border:50px solid $bg_color;
}


</style>