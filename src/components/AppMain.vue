<script>
import Selector from './AppSelector.vue';
import { store } from "../store";

export default {
    components: {
        Selector,
    },

    data () {
        return {
            store,
        };
    },

    methods: {
        getImagePath: function(img) {
            return new URL(`${img}`, import.meta.url).href;
        }
    },
}

</script>

<template>
    <section class="main">
        <Selector />
        <div class="container">
            <div class="row bg-white">
                <div class="my_col col-sm-12 col-md-3" v-for="(card, index) in store.cards" >
                    <div class="card text-center">
                        <!-- {{ card.card_images[0].image_url}} -->
                        <img :src="getImagePath(card.card_images[0].image_url)" alt="">
                    </div>
                    <div>
                        {{ card.name }}
                    </div>
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