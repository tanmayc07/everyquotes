<template>
  <form-component @data-submitted="addData" />
  <display-quote v-if="name" :name="name" :quote="quote" />
</template>

<script>
import formComponent from "./components/form-component";
import displayQuote from "./components/display-quote";

export default {
  name: "App",
  components: {
    "form-component": formComponent,
    "display-quote": displayQuote,
  },
  data() {
    return {
      name: "",
      quote: "",
    };
  },
  methods: {
    addData(dataObj) {
      this.name = dataObj.name;
      this.quote = dataObj.quote;
    },
  },
};
</script>

<style>
#app {
  margin: 0;
  padding: 0;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #bbbbbb;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
