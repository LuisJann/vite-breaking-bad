<script>
import axios from "axios";
import AppHeader from './components/AppHeader.vue';
import CharactersList from './components/CharactersList.vue';
import {store} from "./store";
export default{
  components:{
    AppHeader,
    CharactersList,
  },
  data(){
    return{
      store
    }
  },
  created(){
    axios.get("https://www.breakingbadapi.com/api/characters?limit=5").then((resp) => {
      this.store.characters = resp.data;
      console.log(this.store.characters);
    })
  }
}
</script>

<template>
  <AppHeader />
  <CharactersList />
  <main>

  </main>
</template>

<style lang="scss">
@use "./styles/general.scss" as*;
h1{
  color: white;
}
</style>