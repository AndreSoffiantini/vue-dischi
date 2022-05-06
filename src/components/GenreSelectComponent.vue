<template>

    <form @submit.prevent="$emit('selectSubmit')">

        <select class="form-select" aria-label="Default select example">
            <option selected>Select music genre</option>
            <option 
                v-for="genre in genres" 
                :key="genre" 
                :value="genre" 
                @click="$emit('selectSubmit', $event.target.value)"
            >{{genre}}</option>
        </select>

    </form>            

</template>

<script>
export default {
    name: 'GenreSelectComponent',
    props: {
        albums: Array,
        genre: String
    },
    data() {
        return {
            genres: []
        }
    },
    methods: {
        filterGenres() {
            //console.log(this.albums);
            this.albums.forEach(album => {
                //console.log(album.genre);
                if(!this.genres.includes(album.genre)) {
                    this.genres.push(album.genre)
                }
            });
            //console.log(this.genres);
        }
    },
    mounted() {
        setTimeout(this.filterGenres,500);
    }
}
</script>

<style lang="scss" scoped>

    select {
        width: fit-content;
    }

</style>