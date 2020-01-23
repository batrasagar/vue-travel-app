<template>
  <span class="go-back">
    <button @click="goback">GoBack</button>
  </span>
</template>

<script>
export default {
  methods: {
    goback() {
      return this.$router.go(-1);
    }
  }
};
</script>

<style scoped>
.go-back button {
  display: flex;
  cursor: pointer;
}
button {
  border: solid 1px #ccc;
}
</style>
