<script>
import axios from 'axios';
import Selector from './AppSelector.vue';
import Card from './AppCard.vue';
import { store } from "../store";

export default {
    components: {
        Selector,
        Card,
    },

    data() {
        return {
            store,
        };
    },

    methods: {
        chiamata() {
            this.store.loading = true;
            axios
                .get(this.store.apiUrl, {
                    params: {
                        num: this.store.numeroElementi,
                        offset: this.store.paginaIniziale,
                        archetype: this.store.archetype ?? null
                    },
                })
                .then((resp) => {
                    this.store.cards = resp.data.data;
                    console.log(this.store);
                    this.store.loading = false;
                });
        }
    }
}

</script>

<template>
    <section class="main">
        <Selector @selectedValue="chiamata" />
        <div class="container">
            <h2 v-if ="this.store.loading">Loading...</h2>
            <div class="row  row-cols-sm-1 row-cols-md-3 row-cols-lg-5 bg-white p-5" v-else>
                <div class="my_col mb-5" v-for="(card, index) in store.cards">
                    <Card :card="card" />
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped lang="scss">
@use '../style/partials/variables' as*;

.main {
    background-color: $my_color_primary;
}
</style>