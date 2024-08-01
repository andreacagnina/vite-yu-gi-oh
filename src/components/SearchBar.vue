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
                <select class="form-select form-select-sm">
                    <option selected>Select a race</option>
                    <option value="1">Alien</option>
                    <option value="2">ND</option>
                    <option value="3">ND</option>
                </select>
            </div>
        </div>
    </div>
</template>

<style lang="">
    
</style>