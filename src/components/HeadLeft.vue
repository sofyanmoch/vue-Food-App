<template>
<div>
    <b-row class="header pt-0">
        <b-col lg="2" cols="2" class="py-2 text-left">
            <b-button v-b-toggle.my-sidebar>=</b-button>
        <Sidebar />
        </b-col>
        <b-col lg="6" cols="6" class="py-2">
            <h3>Food Items</h3>
        </b-col>
        <b-col lg="4" cols="4" class="py-2 search">
            <b-input-group>
                      <b-form-input
                        id="input-1"
                        type="text"
                        v-model="name"
                        placeholder="Search"
                      ></b-form-input>
                      <div class="btn btn-outline-primary">
                        <b-icon icon="search" @click="searchProduct"></b-icon>
                      </div>
                    </b-input-group>
            <!-- <div>
    <b-form-input v-model="text" placeholder="Search menu ..."></b-form-input>
  </div> -->
        </b-col>
    </b-row>
</div>
</template>
<script>
import axios from 'axios'
import Sidebar from '../components/Sidebar'
export default {
  props: ['sortby', 'type'],
  data () {
    return {
      name: ''
    }
  },
  methods: {
    searchProduct () {
      if (this.name !== '') {
        axios.get(`http://localhost:3000/produks/getall?name=${this.name}`).then((response) => {
          console.log(response.data.data)
        // console.log(this.products)
        }).catch((err) => {
          console.log(err)
        })
        this.products = null
      } else {
        this.fetchApi()
      }
    }
  },
  components: {
    Sidebar
  }
}
</script>
<style scoped>
.header{
    height: 50px;
    box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.25);
    }
.search img{
    width: 30px;
    height: 30px
}
</style>
