<template>
<div>
    <div class="menu">
        <div class="item card">
            <img :src="`http://localhost:3000/${product.image}`">
                </div>
                <div class="row">
                    <div class="text-left col-lg-6 col-md-6 col-sm-6 col-6">
                <p class="mb-0">{{product.name}}</p>
            <h5 class="card-title">Rp. {{product.price}}</h5>
        </div>
        <div class="text-right col-lg-6 col-md-6 col-sm-6 col-6 my-2"><button type="button" class="btn btn-success" @click="addCart()">Add Cart</button></div>
        </div>
    </div>
</div>
</template>
<script>
export default {
  props: ['product'],
  methods: {
    addCart () {
      this.$emit('emitCart')
    }
  }
}
</script>
<style scoped>
    .item img{
        width: 100%;
        height: 100%
    }
</style>
