<template>
    
    <div class="container">
        <div class="row g-4">
            <AlbumCard :album="album" v-for="album in albums" :key="album.title"/>
        </div>
    </div>

</template>

<script>
import axios from "axios";
import AlbumCard from "@/components/AlbumCardComponent.vue"

export default {
    name: 'AlbumsSectionComponent',
    components: {
        AlbumCard
    },
    data() {
        return {
            api_url: "https://flynn.boolean.careers/exercises/api/array/music",
            albums: null,
            error: null,
        };
    },
    methods: {
        callApi() {
            axios
                .get(this.api_url)
                .then((response) => {
                    //console.log(response);
                    this.albums = response.data.response;
                    console.log(this.albums);
                })
                .catch((error) => {
                    console.error();
                    error;
                    this.error = `Sorry, there is a problem! ${error}`;
                });
        },
    },
    mounted() {
        this.callApi();
    },
}
</script>