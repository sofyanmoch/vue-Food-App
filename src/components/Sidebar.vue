<template>
  <b-sidebar id="my-sidebar" shadow>
    <b-container fluid>
      <b-row>
        <b-col cols="12">
          <img src="../../assets/img/fork.png" alt="Menu" class="my-5" />
        </b-col>
        <b-col cols="12">
          <a href="/history">
            <img src="../../assets/img/clipboard.png" alt="History" class="my-5" />
          </a>
        </b-col>

        <b-col cols="12">
          <img
            src="../../assets/img/add.png"
            alt="Add Menu"
            class="my-5 addProduct"
            @click="showModal1()"
          />
        </b-col>
      </b-row>
    </b-container>
  </b-sidebar>
</template>

<script>
export default {
  name: 'Sidebar',
  methods: {
    showModal1 () {
      this.$emit('showModal1')
    }
  }
}
</script>
