<template>
    
    <header class="p-2 d-flex justify-content-between align-items-center">
        <img src="@/assets/img/logo-small.svg" alt="Logo">
        <GenreSelect :albums="albums" v-model="value" @selectSubmit="filter"/>
    </header>

</template>

<script>
import GenreSelect from '@/components/GenreSelectComponent.vue';
import state from "@/state.js";

export default {
    name: 'HeaderComponent',
    props: {
        albums: Array
    },
    components: {
        GenreSelect
    },
    data() {
        return {
            value: ""
        };
    },
    methods: {
        filter() {
            /* console.log('Filter'); */
            //console.log(this.value);
            state.value = this.value;
            //console.log(state.value);
        },
    },
}
</script>

<style lang="scss" scoped>

    header {
        background-color: $header_cards;
        height: 6vh;
        img {
            height: 30px;
        }
    }   

</style>