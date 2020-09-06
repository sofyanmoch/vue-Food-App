<template>
        <b-form @submit.prevent="searchProduct" inline>
            <b-input placeholder="Search Product" v-model="search"></b-input>
            <b-button type="submit" class="ml-2">Search</b-button>
            </b-form>
</template>
