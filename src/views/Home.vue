<template>
  <div class="container-fluid">
    <!-- <button class="btn btn-primary" @click="getFood()">Get Data</button> -->
    <b-row>
      <b-col lg="8">
        <b-row>
          <b-col lg="12" class="text-center my-0">
            <HeadLeft />
          </b-col>
        </b-row>
          <b-row class="menu">
          <b-col lg="4" cols="6" class="p-3">
            <Card /></b-col>
             <b-col lg="4" cols="6" class="p-3">
            <Card /></b-col>
             <b-col lg="4" cols="6" class="p-3">
            <Card />
            </b-col>
           </b-row>
 </b-col>
      <b-col lg="4">
        <b-row>
          <b-col lg="12" class="text-center my-0">
            <HeadRight />
          </b-col>
          <b-col lg="12">
            <EmptyCart />
          </b-col>
        </b-row>
      </b-col>
    </b-row>
  </div>
</template>
<script>
import HeadLeft from '../components/HeadLeft'
import HeadRight from '../components/HeadRight'
import Card from '../components/Card'
import EmptyCart from '../components/EmptyCart'
import axios from 'axios'
export default {
  data () {
    return {
      foods: []
    }
  },
  name: 'Home',
  components: {
    HeadLeft,
    HeadRight,
    Card,
    EmptyCart
  },
  methods: {
    getFood () {
      axios.get('http://localhost:3000/produks/getall').then((response) => {
        this.foods = response.data
      }).catch((err) => {
        console.log(err)
      })
    }
  }
}
</script>
<style scoped>
  .menu{
    background: rgba(190, 195, 202, 0.3);
  }
</style>
