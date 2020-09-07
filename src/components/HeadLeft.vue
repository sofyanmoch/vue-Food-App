<template>
<div>
    <b-row class="header pt-0 text-align-center">
        <b-col lg="2" cols="2" class="py-2">
            <b-button v-b-toggle.my-sidebar>=</b-button>
        <Sidebar />
        </b-col>
        <b-col lg="6" cols="6" class="py-2">
            <h3>Food Items</h3>
        </b-col>
        <b-col lg="4" cols="4" class="py-2 search">
            <Search />
        </b-col>
    </b-row>
</div>
</template>
<script>
import Sidebar from '../components/Sidebar'
import Search from './Search'
export default {
  components: {
    Sidebar,
    Search
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
