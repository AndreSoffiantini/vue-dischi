<template>

    <main class="d-flex align-items-center justify-content-center">
        
        <AlbumsSection/>

    </main>
    
</template>

<script>
import AlbumsSection from "@/components/AlbumsSectionComponent.vue"
export default {
    name: 'MainComponent',
    components: {
        AlbumsSection
    }
}
</script>

<style lang="scss" scoped>
    main {
        background-color: $main;
        height: 95vh;
    }
</style>

