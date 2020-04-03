<template>
  <div id="app">
    <Header/>
    <UserList v-bind:users= "users" v-on:del-user= "delUser"/>
    <AddUser v-on:add-user= "addUser"/>
  </div>
</template>

<script>
import UserList from './components/UserList.vue'
import Header from './components/Header.vue'
import AddUser from './components/AddUser.vue'

export default {
  name: 'App',
  components: {
    UserList,
    Header,
    AddUser
  },
  data() {
    return {
      users: [
        {userId: "1", userName: "John", feesPaid: false},
        {userId: "2", userName: "Mary", feesPaid: true},
        {userId: "3", userName: "Salma", feesPaid: false}
      ]
    }
  },

  methods: {
    addUser(newUser) {
      this.users= [...this.users, newUser];
    },

    delUser(userId) {
      this.users= this.users.filter(user => user.userId !== userId);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
