<script>
export default {
    props: {
        card: Object,
    }
}
</script>

<template>
    <section class="my_card mx-auto text-center h-100">
        <div class="card my_card_img text-center mb-3">
            <img :src="card.card_images[0].image_url">
        </div>
        <div class="my_card_name mb-3">
            {{ card.name }}
        </div>
        <div class="my_card_archetype mb-3">
            {{ card.archetype }}
        </div>
    </section>
</template>

<style scoped lang="scss">
@use '../style/partials/variables' as*;

.my_card {
    background-color: $my_color_primary;
    width: 200px;
    
}
</style>