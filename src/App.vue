<template>
  <UserTable />
</template>

<script>
import UserTable from "./components/UserTable.vue";

export default {
  name: "App",
  components: {
    UserTable,
  },
};
</script>

<style>
body {
  border-top: 10px solid #8e44ad;
  padding-top: 10px;
}

.text-right {
  text-align: right;
}

.tiny-text {
  display: block;
  font-size: 2.2rem;
  color: #8e44ad;
}
</style>
