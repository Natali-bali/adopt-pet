<template>
    <div>
        <p>{{ $route.params.species }} {{ $route.params.id }}</p>
        <h2> {{animal.name}} ({{ $route.params.species }})</h2>
        <p>Age: {{animal.age}} years old</p>
        <p>Breed: {{animal.breed}}</p>
    </div>
</template>

<script>
import {mapState} from 'vuex'
export default {
 data() {
     return {
         animal:{}
     }
 },
 computed: {
     ...mapState(['dogs', 'cats'])
 },
 mounted() {
         this.animal = this[this.$route.params.species][this.$route.params.id];
     }
 }

</script>
