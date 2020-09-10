<template>
<div>
    <NavHistory />
<b-row class="mx-2 my-3">
  <b-col lg="12">
    <b-row>
        <b-col lg="4" md="12" class="today-income mx-2 my-2">
        <div class="my-5 mx-5">
            <p class="my-2">Today's Income</p>
            <h3 >Rp. 1.000.000</h3>
            <p>+2% Yesterday</p>
        </div>
        </b-col>
        <b-col lg="4" md="12" class="orders-chart mx-2 my-2">
        <div class="my-5 mx-5">
            <p class="my-2">Orders</p>
            <h3 >3.270</h3>
            <p>+5% Last Week</p>
        </div>
        </b-col>
        <b-col class="years-chart mx-2  my-2">
        <div class="my-5 mx-5">
            <p class="my-2">This Year's Income</p>
            <h3 >Rp. 100.000.000.000</h3>
            <p>+10% Last Year</p>
        </div>
        </b-col>
    </b-row>
  </b-col>
<b-col lg="12">
  <b-row class="my-5">
    <b-col lg="11" col="9">
      <h3>Revenue</h3>
    </b-col>
    <b-col lg="1" cols="3">
      <b-dropdown id="dropdown-1" text="Month" class="m-0 text-right">
        </b-dropdown>
    </b-col>
  </b-row>
  <b-row>
    <b-col lg="12" class="my-5">
      <h2 class="text-center">bayangin aja ini chart js</h2>
    </b-col>
  </b-row>
</b-col>
<!-- table -->

  <b-col lg="12" class="my-5">
    <Table />
  </b-col>

</b-row>
</div>
</template>
<script>
import Table from '../components/Table'
import NavHistory from '../components/NavHistory'
// import TodayIncome from '../components/TodayIncome'
// import OrdersChart from '../components/OrdersChart'
// import IncomeYears from '../components/IncomeYears'
export default {
  components: {
    NavHistory,
    Table
    // TodayIncome,
    // OrdersChart,
    // IncomeYears
  }
}
</script>
<style scoped>
.years-chart{
        background: linear-gradient(278.29deg, #AB84C8 30.05%, rgba(241, 201, 236, 0) 133.19%);
filter: drop-shadow(10px 15px 10px rgba(241, 201, 236, 0.25));
border-radius: 10px;
    }
.today-income{
        background: linear-gradient(278.29deg, #FBB2B4 30.05%, rgba(255, 143, 178, 0) 133.19%);
        filter: drop-shadow(10px 15px 10px rgba(255, 143, 178, 0.25));
        border-radius: 10px;
    }
    .orders-chart{
        background: linear-gradient(278.29deg, #29DFFF 30.05%, rgba(41, 223, 255, 0) 133.19%);
filter: drop-shadow(10px 15px 10px rgba(41, 223, 255, 0.25));
border-radius: 10px;
    }
</style>
