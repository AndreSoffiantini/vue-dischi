<template>
    
    <header class="p-2">
        <img src="@/assets/img/logo-small.svg" alt="Logo">
    </header>

</template>

<script>
export default {
    name: 'HeaderComponent'
}
</script>

<style lang="scss" scoped>

    header {
        background-color: $header_cards;
        height: 5vh;
        img {
            height: 30px;
        }
    }   

</style>