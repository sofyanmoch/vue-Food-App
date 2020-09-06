<template>
<div>
    <b-row class="header pt-0 text-align-center">
        <b-col lg="2" cols="2" class="py-2">
            <b-button v-b-toggle.my-sidebar>=</b-button>
        <b-sidebar id="my-sidebar" title="Sidebar" shadow>
      <div class="px-1 py-2">
        Hai
      </div>
    </b-sidebar>
        </b-col>
        <b-col lg="8" cols="8" class="py-2">
            <h3>Food Items</h3>
        </b-col>
        <b-col lg="2" cols="2" class="py-2">
            <h3>+</h3>
        </b-col>
    </b-row>
</div>
</template>
<style scoped>
.header{
    height: 50px;
    box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.25);
    }
</style>
