<template>
  <div class="about">
    <h2>{{pesan}}</h2>
    <h1>This is an about page</h1>
  </div>
</template>
<script>
export default {
  name: 'About',
  props: {
    pesan: String
  }
}
</script>
