<script>
export default {
    props: {
        card: Object,
    }
}
</script>

<template>
    <section class="my_card">
        <div class="card my_card_img text-center">
            <img :src="card.card_images[0].image_url">
        </div>
        <div class="my_card_name">
            {{ card.name }}
        </div>
        <div class="my_card_archetype">
            {{ card.archetype }}
        </div>
    </section>
</template>

<style scoped leng="scss"></style>