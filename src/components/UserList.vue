<template>
<div>
  <div v-bind:key= "user.userId" v-for= "user in users">

    <Users v-bind:user= "user"/>

  </div>
</div>  

</template>

<script>
import Users from "./Users.vue"

export default {
  name: "UserList",
  components: {
    Users
  },
  props: ["users"]
}

</script>

<style scoped>

</style>
