<template>
  <b-sidebar id="my-sidebar" width="80px" shadow>
    <b-container fluid>
      <b-row>
        <b-col cols="12" class="product m-0">
          <router-link to="/">
            <img src="../assets/img/fork.png" alt="Menu" class="my-5" />
            </router-link>
        </b-col>
        <b-col cols="12" class="clipboard m-0">
          <router-link to="/history">
            <img src="../assets/img/clipboard.png" alt="History" class="my-5" />
          </router-link>
        </b-col>
        <b-col cols="12" class="add-produk m-0">
         <button v-b-modal.addProduct><img
            src="../assets/img/add.png"
            alt="Add Menu"
            class="my-5 addProduct"
          /></button>
          <ModalAdd/>
        </b-col>
      </b-row>
    </b-container>
  </b-sidebar>
</template>
<script>
import ModalAdd from './ModalAdd'
export default {
  components: {
    ModalAdd
  }
}
</script>
<style scoped>
  .add-produk img{
    width: 35px;
    height: 35px
  }
  .product img{
     width: 35px;
    height: 35px
  }
  .clipboard img{
     width: 35px;
    height: 35px
  }
</style>
