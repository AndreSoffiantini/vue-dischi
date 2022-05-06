<template>
    
    <div class="container">
        <div class="row g-4">
            <AlbumCard :album="album" v-for="album in albums" :key="album.title"/>
        </div>
    </div>

</template>

<script>
import AlbumCard from "@/components/AlbumCardComponent.vue"

export default {
    name: 'AlbumsSectionComponent',
    props: {
        albums: Array
    },
    components: {
        AlbumCard
    }
}
</script>