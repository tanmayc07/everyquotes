<template>
  <form class="name-form" @submit.prevent="onSubmit">
    <label for="name">Enter your name:</label>
    <input v-model="name" type="text" />
    <button>Submit</button>
  </form>
</template>

<script>
export default {
  name: "form-component",
  data() {
    return {
      name: "",
      quote: "",
    };
  },
  methods: {
    async onSubmit() {
      if (this.name === "") {
        alert("Please enter a name!");
        return;
      }
      let name = this.name;
      let response = await fetch("https://quotes.rest/qod");
      let quote = await response.json();
      let dataObj = {
        name: name,
        quote: quote.contents.quotes[0].quote,
      };
      this.$emit("data-submitted", dataObj);
      this.name = "";
    },
  },
};
</script>

<style>
.name-form {
  margin-top: 150px;
  display: flex;
  flex-direction: column;
  height: 300px;
  width: 200px;
  justify-content: center;
  align-items: center;
  padding: 5px;
}

.name-form label,
input,
button {
  margin: 10px;
}

.name-form label {
  font-weight: bold;
  color: black;
  font-size: 1.2rem;
}

.name-form input {
  padding: 6px;
  border-radius: 5px;
  border-color: aqua;
}

.name-form button {
  padding: 5px;
  background-color: rgb(180, 248, 239);
  border-radius: 5px;
  border: 1px solid black;
}

.name-form button:hover {
  opacity: 0.3;
  color: rgb(167, 164, 164);
}
</style>