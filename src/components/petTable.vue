<template>
    <div>
         <p>{{species}}</p>
         <b-table striped hover
         :items="pet">
            <template v-slot:cell(name)="data">
                <router-link :to="`/pets/${species}/${data.index}`">{{ data.value }}</router-link>
            </template>
         </b-table>
    </div>
</template>

<script>
export default {
    props: {
        species: String,
        pet: Array
    }
}
</script>