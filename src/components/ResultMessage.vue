<script>
import AppCard from './AppCard.vue';
import { store } from '../store.js';


export default {
    components: {
        AppCard,
    },
    data() {
        return {
            store,
        }
    }
}
</script>
<template>
<h5 class="text-light" >Founds {{store.CardsArray.length}} cards</h5>
</template>

<style lang="scss">
h5 {
    margin: 0;
}
</style>