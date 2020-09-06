<template>
<div>
    <b-row class="header pt-0 text-align-center">
        <b-col lg="2" cols="2" class="py-2">
            <b-button v-b-toggle.my-sidebar>=</b-button>
        <Sidebar />
        </b-col>
        <b-col lg="8" cols="8" class="py-2">
            <h3>Food Items</h3>
        </b-col>
        <b-col lg="2" cols="2" class="py-2 search">
            <h3><img src="../assets/img/magnifying-glass.png"></h3>
        </b-col>
    </b-row>
</div>
</template>
<script>
import Sidebar from '../components/Sidebar'
export default {
  components: {
    Sidebar
  }
}
</script>
<style scoped>
.header{
    height: 50px;
    box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.25);
    }
.search img{
    width: 30px;
    height: 30px
}
</style>
