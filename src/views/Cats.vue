<template>
    <div>
        <pet-table
        species="cats"
        :pet = "cats"></pet-table>
    </div>
</template>
<script>
import {mapState} from 'vuex';
import petTable from '../components/petTable.vue'
export default {
    components: {
        petTable
    },
    data() {
        return {

        }
    },
    computed: {
      ...mapState(['cats'])
    }

}
</script>
