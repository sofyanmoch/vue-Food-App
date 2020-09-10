<template>
    <div>
        <b-modal id="modal-checkout" hide-header hide-footer centered>
          <b-row>
            <b-col lg="7">
              <b-row>
                <b-col lg="12"><h4>Checkout</h4></b-col>
                <b-col lg="12">
                  <p>Cashier : Hanna H</p>
                </b-col>
              </b-row>
            </b-col>
            <b-col lg="5">
              <p>Receipt No : #invoice </p>
            </b-col>
          </b-row>
          <b-row class="my-1 mt-3">
            <b-col lg="5" md="5" sm="5" cols="5"><p>Coffe Latte</p></b-col>
            <b-col lg="2" md="2" sm="2"  cols="2"><p>x2</p></b-col>
            <b-col lg="5" md="5" sm="5" cols="5" class="text-right"><p>Rp. 15.000</p></b-col>
          </b-row>
          <b-row class="my-1">
            <b-col lg="5" md="5" sm="5" cols="5"><p>Coffe Latte</p></b-col>
            <b-col lg="2" md="2" sm="2"  cols="2"><p>x2</p></b-col>
            <b-col lg="5" md="5" sm="5" cols="5" class="text-right"><p>Rp. 15.000</p></b-col>
          </b-row>
          <b-row class="my-1">
            <b-col lg="5" md="5" sm="5" cols="5"><p>Coffe Latte</p></b-col>
            <b-col lg="2" md="2" sm="2"  cols="2"><p>x2</p></b-col>
            <b-col lg="5" md="5" sm="5" cols="5" class="text-right"><p>Rp. 15.000</p></b-col>
          </b-row>
          <b-row class="my-1">
            <b-col lg="5" md="5" sm="5" cols="5"><p>PPN</p></b-col>
            <b-col lg="2" md="2" sm="2"  cols="2"><p>10%</p></b-col>
            <b-col lg="5" md="5" sm="5" cols="5" class="text-right"><p>Rp. 1.000</p></b-col>
          </b-row>
          <b-row class="my-3">
            <b-col lg="6"><h5>Payment : Cash</h5></b-col>
            <b-col lg="6" class="text-right"><h5>Total : Rp. 105.000</h5></b-col>
          </b-row>
          <b-row>
            <b-col lg="12"><b-button class="print">Print</b-button></b-col>
            <b-col lg="12" class="my-1 text-center"><p>Or</p></b-col>
            <b-col lg="12"><b-button class="send-email">Send Email</b-button></b-col>
          </b-row>
  </b-modal>
  </div>
</template>
<script>
export default {
  methods: {
    showModal () {
      this.$refs['my-modal'].show()
    }
  }
}
</script>
<style scoped>
  .send-email{
     width: 100%;
    background: #57CAD5;
border-radius: 5px;
  }
  .print{
    width: 100%;
    background: #F24F8A;
border-radius: 5px;
  }
</style>
