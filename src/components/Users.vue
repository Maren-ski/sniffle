<template>
  <div class= "each-user" @click= "$emit('show-userdata', user.userId)">
    <p>
      {{ user.userName }}
      <button @click= "$emit('del-user', user.userId)" class= "del"> x </button>
    </p>
    <p id= "additionalData" @click= "$emit('show-more')"> </p>

  </div>

</template>

<script>

  export default {
    name: "Users",
    props: ["user"]
  }

/*  methods: {
    showAdditionalData() {
      document.getElementbyId("additionalData").innerHTML($emit= 'show-more');
    }
  }*/
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
  .del {
    background: #CD5C5C;
    border-radius: 8px;
    padding: 4px;
  }

</style>
