<script>
import Selector from './AppSelector.vue';
import Card from './AppCard.vue';
import { store } from "../store";

export default {
    components: {
        Selector,
        Card
    },

    data () {
        return {
            store,
        };
    },

    created() {
        console.log(store.cards.length);
    },
}

</script>

<template>
    <section class="main">
        <Selector />
        <div class="container">
            <div class="row bg-white p-5">
                <div class="my_col col-sm-12 col-md-4 col-lg-3" v-for="(card, index) in store.cards"  >
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