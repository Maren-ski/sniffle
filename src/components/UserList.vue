<template>
<div>
  <div v-bind:key= "user.userId" v-for= "user in users">

    <Users v-bind:user= "user" v-on:del-user= "$emit('del-user', user.userId)" v-on:on-click="$emit('on-click', user.userId)"/>

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
