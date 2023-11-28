<script>
import { store } from '../store';

export default {
    data () {
        return {
            store,
        }
    }
}

</script>

<template>
    <section class="selectort pt-3 pb-3 ms-5">
        <select class="custom-select ps-2 pe-5 pt-2 pb-2" @change="$emit('selectedValue')" v-model="this.store.archetype">
            <option disabled value="">Archetipo</option>
            <option value="Alien">Alien</option>
            <option value="Ally of Justice">Ally of Justice</option>
            <option value="Ancient Gear">Ancient Gear</option>
        </select>
    </section>
</template>

<style scoped lang="scss"></style>