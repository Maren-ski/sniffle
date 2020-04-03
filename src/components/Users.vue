<template>
  <div class= "each-user">
    <p @click= "onClick">
      {{ user.userName }}
      <button @click= "$emit('del-user', user.userId)" class= "del"> x </button>
    </p>
    <span class= "show-more" v-show= "isClicked"> Fees Paid: {{ user.feesPaid }} </span>

  </div>

</template>

<script>

  export default {
    name: "Users",
    props: ["user"],

    data() {
      return {
        isClicked: this.isClicked = false
      }
    },

    methods: {
      onClick() {
        return {
          isClicked: this.isClicked = !this.isClicked
        }
      }
    }
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
  .del {
    background: #CD5C5C;
    border-radius: 8px;
    padding: 4px;
  }
  .show-more {
    border-bottom: 1px #ccc dotted;
    border-top: 1px #ccc dotted;
    padding: 8px;
    background: #ccc;
  }

</style>
