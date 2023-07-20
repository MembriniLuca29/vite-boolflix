<script>

</script>

<template>
<div class="header-container">
<input type="text">
<button type="button"></button>
</div>
</template>

<style lang="scss" scoped>
.header-container{
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: black;
    height: 200px;
    width: 100%;
    input{
        padding: 10px 30px 10px 10px;
        font-size: 1.5rem;
        margin-right: 10px;
    }
    button{
        padding: 23px;
        background-color: gray;
    }
    button:hover{
        background-color: lightblue;
    }
}
</style>