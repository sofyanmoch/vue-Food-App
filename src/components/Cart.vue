<template>
    <div>
        <!-- detail cart -->
        <b-row>
            <b-col lg="12">
            <b-row class="my-4">
            <b-col lg="3" md="3" sm="3" cols="3" class="cart-img">
                <img src="../assets/img/img1.png">
            </b-col>
            <b-col lg="5" md="5" dm="5" cols="5">
                <b-row>
                    <b-col lg="12"><h4>Coffe Latte</h4></b-col>
                        <b-col lg="12"><div class="mt-3">
                            <b-button-group>
                                    <b-button class="btn-min">-</b-button>
                                    <b-button class="btn-sum">5</b-button>
                                    <b-button class="btn-plus">+</b-button>
                            </b-button-group>
                                </div>
                            </b-col>
                        </b-row>
                    </b-col>
                <b-col lg="4" md="4" sm="4" cols="4" class="mt-5"><h5>Rp 10.000</h5></b-col>
            </b-row>
            <b-row class="my-4">
            <b-col lg="3" md="3" sm="3" cols="3" class="cart-img">
                <img src="../assets/img/img1.png">
            </b-col>
            <b-col lg="5" md="5" dm="5" cols="5">
                <b-row>
                    <b-col lg="12"><h4>Coffe Latte</h4></b-col>
                        <b-col lg="12"><div class="mt-3">
                            <b-button-group>
                                    <b-button class="btn-min">-</b-button>
                                    <b-button class="btn-sum">5</b-button>
                                    <b-button class="btn-plus">+</b-button>
                            </b-button-group>
                                </div>
                            </b-col>
                        </b-row>
                    </b-col>
                <b-col lg="4" md="4" sm="4" cols="4" class="mt-5"><h5>Rp 10.000</h5></b-col>
            </b-row>
        </b-col>
        </b-row>

        <!-- total cart -->
         <b-row>
             <b-col lg="7" md="7" sm="7" cols="7">
                 <b-row>
                     <b-col lg="12" md="12" sm="12" cols="12"><h4>Total : </h4></b-col>
                     <b-col lg="12" md="12" sm="12" cols="12"><p>*Belum termasuk ppn</p></b-col>
                 </b-row>
             </b-col>
             <b-col lg="5" md="5" sm="5" cols="5">
                    <h4>Rp. 105.000*</h4>
             </b-col>
         </b-row>

        <b-row>
            <b-col lg="12">
                <ButtonCart />
            </b-col>
        </b-row>
    </div>
</template>
<script>
import ButtonCart from './ButtonCart'
export default {
  components: {
    ButtonCart
  }
}
</script>
<style scoped>
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
    .btn-sum{
        color: #82DE3A;
        background: #FFFFFF;
border: 1px solid #82DE3A;
box-sizing: border-box;
    }
</style>
