<template>
  <div class="test">
    {{ msg }}
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "Hola Vue.js",
      user: {
        firstName: "Fabio",
        lastName: "Rojas"
      },
      myhtml: "<h3>Hola vue</h3>",
      showName: true,
      tasks: [
        {
          title: "eat"
        },
        { title: "dinner" },
        { title: "Play" },
        { title: "Games" }
      ]
    };
  },
  methods: {
    saludar(name) {
      alert("hello " + name);
    },
    typing(e) {
      console.log(e.target.value);
    }
  },
  computed: {
    fullName() {
      return this.user.firstName + " " + this.user.lastName;
    }
  },
  props: {
    msg: {
      type: String,
      default: "mensaje por defecto"
    }
  }
};
</script>

<style>
.test {
  background-color: #eee;
}
</style>
