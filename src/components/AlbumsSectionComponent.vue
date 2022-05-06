<template>
    
    <div class="container">
        <div class="row g-4">
            <AlbumCard :album="album" v-for="album in filtered" :key="album.title"/>
        </div>
    </div>

</template>

<script>
import AlbumCard from "@/components/AlbumCardComponent.vue"
import state from "@/state.js";

export default {
    name: 'AlbumsSectionComponent',
    props: {
        albums: Array
    },
    components: {
        AlbumCard
    },
    computed: {
        filtered(){
            if(state.value && state.value !== "Select music genre") {
                return this.albums.filter(album => album.genre === state.value)
                }            
            else {
                return this.albums
            }
        }
    }
}
</script>