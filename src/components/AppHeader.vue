<script>
export default{
    name:"AppHeader"
}
</script>

<template>
    <div class="ms-container">
        <h1>Breaking Bad Api</h1>
    </div>
</template>

<style lang="scss" scoped>
@use"../styles/partials/variables.scss" as*;
.ms-container{
    h1{
        color:$title-color;
        padding: 5px;
    }
}
</style>