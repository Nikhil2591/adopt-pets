<template>
    <div>
        <h1>{{ animal.name }} ({{ $route.params.species }})</h1>
        <h1>Age: {{ animal.age }} years old</h1>
        <h1>Breed: {{ animal.breed }}</h1>
    </div>
</template>

<script>
import { mapState } from 'vuex'


export default {
    data() {
        return {
            animal: {}
        }
    },
    computed: {
        ...mapState([
            'cats',
            'dogs',
        ])
    },
    mounted() {
            const animal = this[this.$route.params.species][this.$route.params.id]
            return animal
        }
    }
</script>