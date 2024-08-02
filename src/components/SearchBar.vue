<script>
    import { store } from '../store.js';
export default {
    data() {
        return {
            store,
        }
    },
    methods:{
        sendArchetype(){
            this.$emit('filter');
        }
    }
}
</script>

<template>
    <div class="row">
        <div class="col-12">
            <div class="content py-4 px-2">
                <select class="form-select form-select-sm" v-model="store.archetypesList" @change="sendArchetype()">
                    <!-- metodo direttamente con emit, aggiungere archetypes_search allo store -->
                    
                    <!-- @change="$emit('filter')" v-model="store.archetypes_search"-->
                    <option selected value="">Show All</option>
                    <option v-for="(archetype, index) in store.ArchetypesArray" :key="index" :value="archetype.archetype_name">{{archetype.archetype_name}}</option>
                </select>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
    
</style>