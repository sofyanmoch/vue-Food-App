<template>
  <b-sidebar id="my-sidebar" shadow>
    <b-container fluid>
      <b-row>
        <b-col cols="4" class="product">
          <img src="../assets/img/fork.png" alt="Menu" class="my-5" />
        </b-col>
        <b-col cols="4" class="clipboard">
          <a href="/history">
            <img src="../assets/img/clipboard.png" alt="History" class="my-5" />
          </a>
        </b-col>

        <b-col cols="4" class="add-produk">
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
    width: 50px;
    height: 50px
  }
  .product img{
     width: 50px;
    height: 50px
  }
  .clipboard img{
     width: 50px;
    height: 50px
  }
</style>
