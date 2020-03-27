<template>

  <div>
    <form @submit= "addUser">
      <input type= "text" v-model= "userName" name= "userName" placeholder= "Add User">
      <input type= "submit" value= "Submit new User" class= "submit-btn">
    </form>
  </div>

</template>

<script>
import uuid from 'uuid';

export default {
  name: "AddUser",
  data() {
    return {
      userName: ""
    }
  },

  methods: {
    addUser(e) {
      e.preventDefault();
      const newUser= {
        id: uuid.v4(),
        userName: this.userName,
        feesPaid: false
      }

      this.$emit('add-user', newUser);
    }
  }
}

</script>

<style scoped>
  form {
    display: flex;
  }

  input[type="text"] {
    flex: 10;
    padding: 5px;
  }

  input[type="submit"] {
    flex: 2;
    padding: 5px;
  }

  .submit-btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }

  .submit-btn:hover {
    background: #666;
  }

</style>
