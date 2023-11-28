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
            alert(this.store.archetype);
            axios
                .get(this.store.apiUrl, {
                    params: {
                        num: this.store.numeroElementi,
                        offset: this.store.paginaIniziale,
                        archetype: this.store.archetype
                    },
                })
                .then((resp) => {
                    this.store.cards = resp.data.data;
                    console.log(this.store);
                });
        }
    }
}

</script>

<template>
    <section class="main">
        <Selector @selectedValue="chiamata" />
        <div class="container">
            <div class="row bg-white p-5">
                <div class="my_col col-sm-12 col-md-4 col-lg-3 mb-5" v-for="(card, index) in store.cards">
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