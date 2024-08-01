<script>
import AppCard from './AppCard.vue';
import SearchBar from './SearchBar.vue';
import ResultMessage from './ResultMessage.vue';
import { store } from '../store.js';


export default {
    components: {
        AppCard,
        SearchBar,
        ResultMessage
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
            let FCard = store.CardsArray.archetype.contains(store.archetypesList)
                console.log(FCard)
                
                return FCard;
            };
            return store.CardsArray;
        }
    }
}
</script>

<template>
    <main>
        <div class="container bg-ocre px-5">
            <SearchBar @filter="getCardFiltered()"/>
            <div class="row">
                <div class="col-12">
                    <div class="content bg-light p-4">
                        <div class="col-12">
                            <div class="content bg-dark p-3">
                                <ResultMessage/>
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
.bg-ocre {
    background-color: $bg_color;
}


</style>