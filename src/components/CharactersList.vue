<script>
import CharacterCard from './CharacterCard.vue';
import { store } from '../data/store'
export default {
    components: { CharacterCard },
    data() {
        return { store }
    }
};
</script>




<template>
    <div class="container text-center mt-5">
        <div class="row row-cols-5 g-4 ">
            <div class="col" v-for="character in store.characters" :key="character.id">
                <CharacterCard :name="character.name" :imageUrl="character.imageUrl" :number="character.number"
                    :type1="character.type1" />
            </div>



            <!-- ERA UN TEST CHE HO VOLUTO FARE COME CI AVEVA SPIEGATO IN LEZIONE MARCO L.
                <div class="col" v-for="character in characters" :key="character.id">
                    {{ character.name }}</div>-->
        </div>
    </div>
</template>

<style></style>