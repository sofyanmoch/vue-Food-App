<template>
  <div>
    <b-table striped hover :items="items"></b-table>
  </div>
</template>

<script>
export default {
  data () {
    return {
      items: [
        { invoice: 40, orders: 'Dickerson', amount: 'Macdonald' },
        { invoice: 21, orders: 'Larsen', amount: 'Shaw' },
        { invoice: 89, orders: 'Geneva', amount: 'Wilson' },
        { invoice: 38, orders: 'Jami', amount: 'Carney' }
      ]
    }
  }
}
</script>
