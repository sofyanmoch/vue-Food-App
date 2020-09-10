<template>
  <div class="home container-fluid">
    <!-- <button class="btn btn-primary" @click="getFood()">Get Data</button> -->
    <b-row>
      <b-col lg="8">
        <b-row>
          <b-col lg="12" class="text-center my-0">
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
          </b-col>
        </b-row>
          <b-row class="menu">
            <b-col lg="12">
              <b-row>
                <b-col>
                  <b-dropdown text="Sort by : ">
                    <b-dropdown-group header="Name">
                      <b-dropdown-item-button @click="sortByNameAsc()">A-Z</b-dropdown-item-button>
                      <b-dropdown-item-button @click="sortByNameDesc()">Z-A</b-dropdown-item-button>
                    </b-dropdown-group>
                    <b-dropdown-divider></b-dropdown-divider>
                    <b-dropdown-group header="Price">
                      <b-dropdown-item-button @click="sortByPriceAsc()">Low - High</b-dropdown-item-button>
                      <b-dropdown-item-button @click="sortByPriceDesc()">High - Low</b-dropdown-item-button>
                    </b-dropdown-group>
                  </b-dropdown>
                </b-col>
              </b-row>
              <b-row>
            <b-col lg="4" cols="6" class="p-3" v-for="(item,index) in products" :key="index">
            <Card v-on:emitCart="addCart(item.id)" :product="item"/>
          <!-- <b-col lg="4" cols="6" class="p-3">
            <Card /> -->
          </b-col>
          </b-row>
          </b-col>
           </b-row>
           <b-col cols="12" class="mt-5">
              <b-pagination
                  v-model="currentPage"
                  :total-rows="rows"
                  :per-page="limit"
                  aria-controls="my-table"
                ></b-pagination>
            </b-col>
        </b-col>
      <b-col lg="4">
        <b-row>
          <b-col lg="12" class="text-center my-0">
            <HeadRight />
          </b-col>
          <b-col lg="12">
            <div v-if="cart.length===0">
            <EmptyCart />
            </div>
            <div v-else>
        <div v-for="(item,index) in cart" :key="index">
                <!-- {{item.name}} -->
              <b-row>
            <b-col lg="12">
            <b-row class="my-4">
            <b-col lg="3" md="3" sm="3" cols="3" class="cart-img">
                <img :src="`http://localhost:3000/${item.image}`">
            </b-col>
            <b-col lg="5" md="5" dm="5" cols="5">
                <b-row>
                    <b-col lg="12"><h4>{{item.name}}</h4></b-col>
                        <b-col lg="12"><div class="mt-3">
                            <b-button-group>
                                    <b-button class="btn-min" @click="decrementQty()">-</b-button>
                                    <b-button class="btn-sum">{{item.qty}}</b-button>
                                    <b-button class="btn-plus" @click="incrementQty()">+</b-button>
                            </b-button-group>
                                </div>
                            </b-col>
                        </b-row>
                    </b-col>
                <b-col lg="4" md="4" sm="4" cols="4" class="mt-5"><h5>Rp {{item.price}}</h5></b-col>
            </b-row>
        </b-col>
        </b-row>
        </div>
        <b-row>
          <b-col lg="7" md="7" sm="7" cols="7">
                 <b-row>
                     <b-col lg="12" md="12" sm="12" cols="12"><h4>Total :  </h4></b-col>
                     <b-col lg="12" md="12" sm="12" cols="12"><p>*Belum termasuk ppn</p></b-col>
                 </b-row>
             </b-col>
             <b-col lg="5" md="5" sm="5" cols="5">
                    <h4>Rp. 105.000*</h4>
             </b-col>
        </b-row>
        <b-row>
            <b-col lg="12" class="my-2">
                <b-button v-b-modal.modal-checkout class="co" @click="showModal()" variant="success">Checkout</b-button>
            <ModalCheckout />
            </b-col>
            <b-col lg="12" class="mt-0">
                <b-button class="cancel" variant="danger">Cancel</b-button>
            </b-col>
        </b-row>
            </div>
          </b-col>
        </b-row>
      </b-col>
    </b-row>
  </div>
</template>
<script>
import Sidebar from '../components/Sidebar'
import HeadRight from '../components/HeadRight'
import Card from '../components/Card'
import EmptyCart from '../components/EmptyCart'
import ModalCheckout from '../components/ModalCheckout'
import axios from 'axios'
export default {
  data () {
    return {
      // getProducts
      products: [],
      cart: [],
      category: [],
      page: 1,
      limit: 10,
      name: '',
      sortby: '',
      type: ''

      // pagination
      // sortText: 'Sort',
      // totalData: 0,
      // showPagination: true
    }
  },
  name: 'Home',
  components: {
    Sidebar,
    HeadRight,
    Card,
    EmptyCart,
    ModalCheckout
  },
  methods: {
    searchProduct () {
      if (this.name !== '') {
        axios.get(`http://localhost:3000/produks/getall?name=${this.name}`).then((response) => {
          this.products = response.data.data
        // console.log(this.products)
        }).catch((err) => {
          console.log(err)
        })
        this.products = null
      } else {
        this.fetchApi()
      }
    },
    getProducts () {
      axios.get('http://localhost:3000/produks/getall').then((response) => {
        this.products = response.data.data
      }).catch((err) => {
        console.log(err)
      })
    },
    addCart (id) {
      const dataCart = this.products.filter(e => e.id === id)
      dataCart[0].qty = 1
      this.cart = [
        ...this.cart, dataCart[0]
      ]
    },
    getCategory () {
      axios.get('http://localhost:3000/category/getall').then((response) => {
        this.category = response.data.data
      }).catch((err) => {
        console.log(err)
      })
    },
    incrementQty (dataCart) {
      dataCart[0].qty++
    },
    decrementQty (dataCart) {
      if (dataCart.qty === 1) {
        this.removeCart(dataCart)
      } else {
        dataCart.qty -= 1
      }
    },
    showModal () {
      this.$refs['my-modal'].show()
    },
    // pagination
    pageChange (numbPage) {
      this.$router.push(`?page=${numbPage}`)
      this.page = numbPage
      this.getProducts()
    },
    sortByNameAsc () {
      axios.get('http://localhost:3000/produks/getall?sortby=name').then((res) => {
        this.products = res.data.data
      }).catch((err) => {
        console.log(err)
      })
    },
    sortByNameDesc () {
      axios.get('http://localhost:3000/produks/getall?sortby=name&type=desc').then((res) => {
        this.products = res.data.data
      }).catch((err) => {
        console.log(err)
      })
    },
    sortByPriceAsc () {
      axios.get('http://localhost:3000/produks/getall?sortby=price&type=asc').then((res) => {
        this.products = res.data.data
      }).catch((err) => {
        console.log(err)
      })
    },
    sortByPriceDesc () {
      axios.get('http://localhost:3000/produks/getall?sortby=price&type=desc').then((res) => {
        this.products = res.data.data
      }).catch((err) => {
        console.log(err)
      })
    }
  },
  mounted () {
    this.getProducts()
  },
  computed: {
    rows () {
      return this.products.length
    }
  }
}
</script>
<style scoped>
  .menu{
    background: rgba(190, 195, 202, 0.3);
  }
      .cart-img img{
        width: 100px;
        height: 100px;
    }
    .btn-plus{
        color: #82DE3A;
        background: rgba(130, 222, 58, 0.2);
border: 1px solid #82DE3A;
box-sizing: border-box;
    }
    .btn-min{
        background: rgba(130, 222, 58, 0.2);
border: 1px solid #82DE3A;
box-sizing: border-box;
color: #82DE3A;
    }
    .header{
    height: 50px;
    box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.25);
    }
.search img{
    width: 30px;
    height: 30px
}
    .btn-sum{
        color: #82DE3A;
        background: #FFFFFF;
border: 1px solid #82DE3A;
box-sizing: border-box;
    }
    .co{
        width: 100%;
        background: #57CAD5;
    }
    .cancel{
        width: 100%;
        background: #F24F8A;
    }
</style>
