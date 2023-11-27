<script>
import Selector from './AppSelector.vue';

export default {
    components: {
        Selector,
    }
}

</script>

<template>
    <section class="main">
        <Selector/>
    </section>
</template>

<style scoped lang="scss">
    @use '../style/partials/variables' as*;
    .main {
        background-color: $my_color_primary;
    }
</style>