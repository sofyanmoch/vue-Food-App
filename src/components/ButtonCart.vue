<template>
    <div>
        <b-row>
            <b-col lg="12" class="my-2">
                <b-button v-b-modal.modal-checkout class="co" variant="success">Checkout</b-button>
            <ModalCheckout />
            </b-col>
            <b-col lg="12" class="mt-0">
                <b-button class="cancel" variant="danger">Cancel</b-button>
            </b-col>
        </b-row>
    </div>
</template>
<style scoped>
    .co{
        width: 100%;
        background: #57CAD5;
    }
    .cancel{
        width: 100%;
        background: #F24F8A;
    }
</style>
<script>
import ModalCheckout from './ModalCheckout'
export default {
  components: {
    ModalCheckout
  }
}
</script>
