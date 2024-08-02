<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { store } from './store.js';
import axios from 'axios';

export default {
  components: {
    AppHeader,
    AppMain,
  },
  created() {
    this.getCard(),
    this.getArchetype()
  },
  methods: {
    getCard() {
      axios.get(store.apiUrl).then((result) => {
        store.CardsArray = result.data.data
      });
    },
      getArchetype(){
        axios.get(store.apiArchetypesUrl).then((result) => {
          // for(let i=0; i<10;<i++){store.ArchetypesArray.push(result.data[i]);}
        store.ArchetypesArray = result.data
          
      });
    }
  },
  data() {
    return {
      store,
    }
  }
}
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss">
@use './styles/generals.scss';
</style>
