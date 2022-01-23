<template>
  <header class="heading">
      <h1>{{ title }}</h1>
  </header>
</template>

<script>
export default {
    props: {
        title: String
    }
}
</script>

<style scoped>
    .heading {
        height: 16vh;
        width: 50vw;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
    }
</style>