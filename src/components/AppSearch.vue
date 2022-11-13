<script>
import {store} from "../store"

export default{
    name:"AppSearch",
    data(){
        return{
            store
        }
    }
}
</script>

<template>
<div class="d-flex justify-content-center">
    <input type="text" class="form-controll" v-model="store.filter">
    <button class="btn btn-primary" @click="$emit(`performSearch`)">Search</button>
</div>
</template>

<style lang="scss" scoped>

</style>