<template>
    <div>
<b-modal id="addProduct" hide-footer centered title="Add Item">
    <b-row>
        <b-col lg="12">
            <form @submit.prevent="sendData" enctype="multipart/form-data">
            <b-row class="my-3">
                <b-col lg="3" cols="3">Name</b-col>
                <b-col lg="9" cols="9">
                    <b-form-input type="text" v-model="name" required placeholder="Item Name ..."></b-form-input>
                </b-col>
            </b-row>
            <b-row class="my-3">
                <b-col lg="3" cols="3">Image</b-col>
                <b-col lg="9" cols="9">
                    <b-form-file type="file" @change="processFile($event)" required></b-form-file>
                </b-col>
            </b-row>
            <b-row class="my-3">
                <b-col lg="3" cols="3">Price</b-col>
                <b-col lg="9" cols="9">
                    <b-form-input type="text" v-model="price" required placeholder="Item Price ..."></b-form-input>
                </b-col>
            </b-row>
            <b-row class="my-3">
                <b-col lg="3" cols="3">Category</b-col>
                <b-col lg="9" cols="9">
                    <b-form-input type="text" v-model="category" required placeholder="Item Price ..."></b-form-input>
                    <!-- <div>
                        <b-input-group v-model="category">
                            <template v-slot:append>
                            <b-dropdown text="Dropdown" variant="success">
                                <b-dropdown-item>Foods</b-dropdown-item>
                                <b-dropdown-item>Beverages</b-dropdown-item>
                            </b-dropdown>
                            </template>
                        </b-input-group>
                        </div> -->
                </b-col>
            </b-row>
             <div class="form-button">
            <!-- <input type="submit" value="Send"/> -->
            <!-- <input type="button" value="cancel" @click="$emit('addclose')"/> -->
            <b-button class="mt-3" variant="outline-success" type="submit" block @click="loadOnce" name="button">Add</b-button>
            <b-button class="mt-3" variant="outline-danger" type="button" block @click="hideModal">Cancel</b-button>
          </div>
            </form>
        </b-col>
    </b-row>
  </b-modal>
</div>

</template>
<script>
import axios from 'axios'
export default {
  data () {
    return {
      name: null,
      category: null,
      price: null,
      image: null
    }
  },
  methods: {
    hideModal () {
      this.$refs['my-modal'].hide()
    },
    loadOnce () {
      location.reload()
    },
    processFile (event) {
      this.image = event.target.files[0]
    },
    sendData () {
      const fd = new FormData()
      fd.append('name', this.name)
      fd.append('category', this.category)
      fd.append('price', this.price)
      fd.append('image', this.image)
      axios.post('http://localhost:3000/produks/add', fd)
        .then((res) => {
          console.log(res.data)
        })
        .catch((err) => {
          console.log(err)
        })
    }
  }
}
</script>
