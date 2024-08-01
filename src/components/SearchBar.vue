<script>
    import { store } from '../store.js';
export default {
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <div class="row">
        <div class="col-12">
            <div class="content py-4 px-2">
                <select class="form-select form-select-sm" v-model="store.archetypesList">
                    <option selected>Select a race</option>
                    <option value="{{index}}" v-for="(archetype, index) in store.ArchetypesArray">{{archetype.archetype_name}}</option>

                </select>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
    
</style>