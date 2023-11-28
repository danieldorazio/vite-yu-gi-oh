<script>
import { store } from '../store';

export default {
    data() {
        return {
            store,
        }
    },
    methods: {
        prec() {
            console.log("prec");
            if (this.store.paginaIniziale == 1) {
                this.store.paginaIniziale = 0;
            } else {
                this.store.paginaIniziale--;
            }
            this.$emit('selectedValue');
            // this.store.numeroElementi = this.store.numeroElementi - 20;
            // this.store.paginaIniziale = this.store.paginaIniziale - 20
            // console.log(this.store.numeroElementi, this.store.paginaIniziale);
        },

        succ() {
            console.log("succ");

            this.store.paginaIniziale++;
 
            this.$emit('selectedValue');

            this.store.numeroElementi = this.store.numeroElementi + 20;
            this.store.paginaIniziale = this.store.paginaIniziale + 20
            console.log(this.store.numeroElementi, this.store.paginaIniziale);
        }
    }
}

</script>

<template>
    <section class="selectort pt-3 pb-3 m-auto d-flex justify-content-between w-75">
        <select class="custom-select ps-2 pe-5 pt-2 pb-2" @change="$emit('selectedValue')" v-model="this.store.archetype">
            <option disabled value="">Archetipo</option>
            <option value="Alien">Alien</option>
            <option value="Ally of Justice">Ally of Justice</option>
            <option value="Ancient Gear">Ancient Gear</option>
        </select>
        <div>
            <p>Found {{ this.store.cards.length }} cards</p>
        </div>
        <div class="d-grid gap-2 d-md-flex justify-content-md-end">
            <button class="btn btn-light me-md-2" type="button" @click.stop="prec()">← Prec</button>
            <button class="btn btn-light" type="button" @click.stop="succ()">Succ →</button>
        </div>
    </section>
</template>

<style scoped lang="scss"></style>