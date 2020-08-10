<template>
  <div>
    <h3>Here you can add new pet for adoption</h3>
    <button v-if = "!showPetForm"
            class="btn btn-primary"
            @click = "togglePetForm">Add new pet</button>
    <div>
      <b-form @submit.prevent="onSubmit" v-if="showPetForm">
        <b-form-group
          id="input-group-1"
          label="Name:"
          label-for="input-1"
        >
            <b-form-input
              id="input-1"
              v-model="form.name"
              type="text"
              required
              placeholder="Enter Pet's name"
            ></b-form-input>
        </b-form-group>

      <b-form-group id="input-group-2" label="Breed:" label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="form.breed"
          required
          placeholder="Enter breed"
        ></b-form-input>
      </b-form-group>
      <b-form-group id="input-group-3" label="Age:" label-for="input-3">
        <b-form-input
          id="input-3"
          type = "number"
          v-model="form.age"
          placeholder="Enter age"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-4" label="Species:" label-for="input-4">
        <b-form-select
          id="input-4"
          v-model="form.species"
          :options="['cats', 'dogs']"
          placeholder="Specify species"
          required
        ></b-form-select>
      </b-form-group>



      <b-button type="submit" variant="primary">Submit</b-button>
      <b-button type="reset" variant="danger">Reset</b-button>
    </b-form>

  </div>
  </div>
</template>

<script>
import {mapActions} from 'vuex'
export default {
data() {
  return {
    showPetForm: false,
    form: {
      name: '',
      breed: '',
      age: null,
      species: null
    },
  }
},
methods: {
  ...mapActions ( [
    'addPet'
  ]),
  togglePetForm() {
    this.showPetForm = true;
  },
  onSubmit() {
    const {species, name, age, breed} = this.form;
    const payload = {
      species,
      pet: {
        name,
        age,
        breed
      }
    }
    this.addPet(payload);
    this.form = {name: '',
      breed: '',
      age: null,
      species: null

    }
  }
}
}
</script>
