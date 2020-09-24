<template>
  <div class="quote">
    <p>Hello {{ name }}, your quote for today is: "{{ quote }}"</p>
  </div>
</template>

<script>
export default {
  name: "display-quote",
  props: {
    name: {
      type: String,
      required: true,
    },
    quote: {
      type: String,
      required: true,
    },
  },
};
</script>

<style>
.quote {
  height: 100%;
  width: 200px;
  background-color: rgb(251, 170, 170);
  color: rgb(5, 5, 5);
  border-radius: 5px;
  padding: 20px;
}
</style>