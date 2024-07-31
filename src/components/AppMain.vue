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
    <main>
        <div class="container bg-ocre px-5">
            <div class="row">
                <div class="col-12">
                    <div class="content py-4 px-2">
                        <select class="form-select form-select-sm">
                            <option selected>Select a race</option>
                            <option value="1">Alien</option>
                            <option value="2">ND</option>
                            <option value="3">ND</option>
                        </select>
                    </div>
                </div>
            </div>
            <div class="row">
                <div class="col-12">
                    <div class="content bg-light p-4">
                        <div class="col-12">
                            <div class="content bg-dark p-3">
                                <h5 class="text-light">Found text</h5>
                            </div>
                        </div>
                        <div class="col-12">
                            <div class="row row-cols-5">
                                <AppCard />
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>

</template>

<style lang="scss" scoped>
.bg-ocre {
    background-color: #d48f38;
}

h5 {
    margin: 0;
}
</style>