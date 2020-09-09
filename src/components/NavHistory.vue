<template>
    <div>
    <b-row class="header container-fluid">
        <b-col lg="1" cols="1" class="py-2 text-left px-3">
            <b-button v-b-toggle.my-sidebar>=</b-button>
        <Sidebar />
        </b-col>
        <b-col lg="11" cols="11" class="py-2 text-center">
            <h3>History</h3>
        </b-col>
    </b-row>
</div>
</template>
<script>
import Sidebar from './Sidebar'
export default {
  components: {
    Sidebar
  }
}
</script>
<style scoped>
.header{
    background: #FFFFFF;
box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.25);
}
</style>
