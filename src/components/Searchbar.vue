<template>
  <div class="mb-3">
    <input type="text" @input="onSearch" placeholder="Search videos here..." />
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  methods: {
    onSearch(e) {
      // console.log(e.target.value);
      this.$emit("termSearch", e.target.value);
    },
  },
};
</script>

<style scoped>
input {
  background-color: #252438;
  padding: 4px 10px 4px 10px;
  border-radius: 5px;
  color: white;
  outline: none;
  border: none;
  line-height: 35px;
  display: block;
  margin: 0 auto;
  width: 100%;
}
</style>