<script>
import {store} from "../store";
export default{
    name:"CharactersList",
    data (){
        return{
            store
        }
    }
}
</script>

<template>
    <div class="ms-wrapper">
        <div class="row row-cols-5">
            <div class="col" v-for="(item,index) in store.characters " :key="index">
                <div class="ms-card">
                    <img :src="item.img" alt="">
                    <h5>{{item.name}}</h5>
                    <p>{{item.nickname}}</p>
                    <p>{{item.status}}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use"../styles/partials/variables.scss" as*;

.ms-wrapper{
    width: 90%;
    margin: 0 auto;
    background-color: $title-color;
    display: flex;
    flex-direction: row;
    padding: 50px;
    .ms-card{
        background-color: $bg-color;
        width: 100%;
        height: 100%;
        text-align: center;

        img{
            width: 80%;
            margin: 10px;
        }

        h5{
            font-size: .8rem;
            color: $title-color;

        }
        p{
            font-size: .8rem;
            color: $text-color;
        }

    }
}


</style>