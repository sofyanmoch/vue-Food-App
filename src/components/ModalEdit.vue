<template>
    <div>
<b-modal id="modal-update" hide-footer centered title="Add Item">
    <b-row>
        <b-col lg="12">
            <form @submit.prevent="updateData()" enctype="multipart/form-data">
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
                    <b-form-input type="number" v-model="price" required placeholder="Item Price ..."></b-form-input>
                </b-col>
            </b-row>
            <b-row class="my-3">
                <b-col lg="3" cols="3">Category</b-col>
                <b-col lg="9" cols="9">
                  <b-form-select v-model="category_id">
                    <b-form-select-option v-for="(item, index) in categories" :key="index" :value="item.id" required>
              {{item.category_name}}
            </b-form-select-option>
                  </b-form-select>
                  <!-- <div>
                    <b-form-select v-model="category">
                    <b-form-select-option v-for="(item,index) in categories" :key="index" :value="item.category_id">{{item.category_name}}</b-form-select-option>
                  </b-form-select>
                  </div> -->
                </b-col>
            </b-row>
             <div class="form-button">
            <!-- <input type="submit" value="Send"/> -->
            <!-- <input type="button" value="cancel" @click="$emit('addclose')"/> -->
            <b-button class="mt-3" variant="outline-success" type="submit" @click="load()" name="button">Add</b-button>
            <b-button class="mt-3" variant="outline-danger" type="button" @click="hideModal()">Cancel</b-button>
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
  props: ['update'],
  data () {
    return {
      name: null,
      category_id: null,
      price: null,
      image: null,
      categories: []
    }
  },
  methods: {
    // getDetail () {
    //   axios.get(`http://localhost:3000/getdetail/${id}`)
    // },
    hideModal () {
      location.reload()
    },
    load () {
      location.reload()
    },
    processFile (event) {
      this.image = event.target.files[0]
    },
    getCategory () {
      axios.get('http://localhost:3000/category/getall').then((res) => {
        this.categories = res.data.data
      }).catch((err) => {
        console.log(err)
      })
    }
  },
  mounted () {
    this.getCategory()
  }
}
</script>
