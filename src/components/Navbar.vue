<template>
<div>
<div>
  <b-row>
      <b-col lg="8">
          <b-row class="bg-primary">
              <h2 class="col-lg-1">left</h2>
              <h2 class="col-lg-8 text-center">Food Items</h2>
              <h2 class="col-lg-2">Search</h2>
          </b-row>
          <b-row>
            <b-col lg="3" class="mx-5 my-3">
                <Card />
            </b-col>
        </b-row>
      </b-col>
    <b-col lg='4'>
        <b-row>
            <b-col lg='12'>
                <h2 class="text-center">Cart</h2>
            </b-col>
        </b-row>
    </b-col>

    </b-row>
</div>
</div>
</template>
<script>
import Card from './Card'
export default {
  name: 'About',
  components: {
    Card
  },
  props: {
    pesan: String
  }
}
</script>
