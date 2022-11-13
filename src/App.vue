<script>
import axios from "axios";
import AppHeader from './components/AppHeader.vue';
import CharactersList from './components/CharactersList.vue';
import AppSearch from "./components/AppSearch.vue";
import {store} from "./store";
export default{
  components:{
    AppHeader,
    CharactersList,
    AppSearch,
  },
  data(){
    return{
      store
    }
  },
  created(){
    this.filterCharacter()
  },
  methods: {
    filterCharacter() {
      console.log("personaggio");
      let apiName = "https://www.breakingbadapi.com/api/characters?limit=5";
      if(this.store.filter !== ""){
        apiName += `&name=${this.store.filter}`;
      }
      axios.get(apiName).then((resp) => {
        console.log(resp);
        this.store.characters = resp.data
      })
    }
  }
}
</script>

<template>
  <AppHeader />
  <main>
    <AppSearch class="my-4" @performSearch="filterCharacter"/>
    <CharactersList />
  </main>
</template>

<style lang="scss">
@use "./styles/general.scss" as*;

main{
  text-align: center;
  color: white;
  z-index: 999;
}
</style>