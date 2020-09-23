<template>
  <div class="test">This is a {{ message }}</div>
</template>

<script>
export default {
  name: "test-component",
  data() {
    return {
      message: "Testing",
    };
  },
};
</script>

<style>
.test {
  font-size: 2rem;
  text-align: center;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100vw;
}
</style>