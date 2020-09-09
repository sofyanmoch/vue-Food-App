<template>
    <div>
        <b-row class="my-2 text-center">
            <b-col lg="8"><HeadLeft /></b-col>
            <b-col lg="4"><HeadRight /></b-col>
        </b-row>
    </div>
</template>
<script>
import HeadLeft from './HeadLeft'
import HeadRight from './HeadRight'
export default {
  name: 'Header',
  components: {
    HeadLeft,
    HeadRight
  }
}
</script>
