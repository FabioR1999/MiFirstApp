<template>
  <div class="UserTest">
    <h1>Users Components</h1>

    <ul>
      <li v-for="(user, i) in users" :key="i">
        {{ user.name }} - {{ user.email }}
        <button v-on:click="deleteUser(user)" class="test1">X</button>
      </li>
    </ul>

    <form v-on:submit.prevent="addUser">
      <input type="text" v-model="newUser.name" placeholder="Nombre" />
      <input type="email" v-model="newUser.email" placeholder="Correo" />
      <button type="submit ">Add</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      users: [
        {
          name: "Fabio",
          email: "Fabio@gmail.com",
          contacted: false
        },
        {
          name: "Juan",
          email: "Juan@gmail.com",
          contacted: false
        },
        {
          name: "Roberto",
          email: "Roberto@gmail.com",
          contacted: true
        }
      ],
      newUser: {}
    };
  },
  methods: {
    addUser() {
      this.users.push(this.newUser);
      this.newUser = {};
    },
    deleteUser(user) {
      this.users.splice(this.users.indexOf(user), 1);
      alert("Eliminando Registro");
    }
  },
  created() {
    this.$http
      .get("https://jsonplaceholder.typicode.com/users")
      .then(res => (this.users = res.body));

    // fetch("https://jsonplaceholder.typicode.com/users")
    //   .then(res => res.json())
    //   .then(data => console.log(data));
  }
};
</script>

<style>
.UserTest {
  background: #858585;
  color: white;
  padding: 20px;
}

.test1 {
  font-weight: bold;
}
</style>
