<template>
<div>
    <div class="menu">
        <div class="item card">
            <img :src="`http://localhost:3000/${product.image}`">
                </div>
                <div class="row">
                    <div class="text-left col-lg-12 col-md-12 col-sm-12 col-12">
                <p class="mb-0">{{product.name}}</p>
            <h5 class="card-title">Rp. {{product.price}}</h5>
        </div>
        <div class="text-right col-lg-4 col-md-4 col-sm-4 col-4 my-2"><button type="button" class="btn btn-primary" @click="addCart()"><img src="../assets/img/addcart.png" width="50%"></button></div>
        <div v-b-modal.modal-update @click="update(product.id)" class="text-right col-lg-4 col-md-4 col-sm-4 col-4 my-2"><button type="button" class="btn btn-warning"><img src="../assets/img/edit.png" width="50%"></button></div>
        <ModalEdit />
        <div @click="deleteProduct(product.id)" class="text-right col-lg-4 col-md-4 col-sm-4 col-4 my-2"><button type="button" class="btn btn-danger"><img src="../assets/img/delete.png" width="50%"></button></div>
        </div>
    </div>
</div>
</template>
<script>
import ModalEdit from './ModalEdit'
import axios from 'axios'
export default {
  components: {
    ModalEdit
  },
  props: ['product'],
  methods: {
    update (id) {
      alert(id)
      // console.log(index)
      // this.oldId = this.data[index].id
      // this.oldName = this.data[index].name
      // this.oldCategory = this.data[index].category
      // this.oldPrice = this.data[index].price
      // this.oldImage = this.data[index].image
      // console.log(this.data[0])
    },
    addCart () {
      this.$emit('emitCart')
    },
    deleteProduct (productId) {
      axios.delete(`http://127.0.0.1:3000/produks/delete/${productId}`)
        .then((response) => {
          location.reload()
        })
        .catch((error) => error)
    }
  }
}
</script>
<style scoped>
    .item img{
        width: 100%;
        height: 100%
    }
    .card img:hover{
        opacity: 0.7;
        cursor: pointer;
    }
</style>
