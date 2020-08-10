<template>
    <div>
        <pet-table
        species="dogss"
        :pet = "dogs"></pet-table>
    </div>
</template>

<script>
import {mapState} from 'vuex';
import petTable from '../components/petTable.vue';
export default {
    components: {
        petTable
    },
    computed: {
        ...mapState(['dogs'])
    }
}
</script>
