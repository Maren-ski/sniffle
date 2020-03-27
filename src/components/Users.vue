<template>
  <div class= "each-user">
    <p> {{ user.userName }} </p>

  </div>

</template>

<script>

  export default {
    name: "Users",
    props: ["user"]
  }
</script>

<style scoped>

  .each-user {
    background: #f4f4f4;
    padding: 15px;
    border-bottom: 1px #ccc dotted;
  }

  .each-user:hover {
    background: #98FB98;
  }

</style>
