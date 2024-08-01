<script>
import { store } from '../store.js';
export default {
//     props: {
// Card: Object
//     } 
// }
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <div class="col mb-3 " v-for="card in store.CardsArray">
        <div class="content border text-center bg-ocre h-100">
            <img v-for=" img in card.card_images" :src="img.image_url_small" alt="">
            <h6 class="mt-2 text-bold">{{ card.name }}</h6>
            <p>{{ card.race }}</p>
        </div>
    </div>

</template>

<style lang="scss" scoped>
@use '../styles/_partials/_bgColor' as *;
h6 {
    text-transform: uppercase;
    color: white;
    height: 58px;
}

.bg-ocre {
    background-color: $bg_color;
}

img {
    width: 100%;
    ;
}

.h-100 {
    height: 100%;
}


</style>