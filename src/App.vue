<template>
  <div class="container">
    <AddUserForm />
    <UserTable />
  </div>
</template>

<script>
import UserTable from "./components/UserTable.vue";
import AddUserForm from "./components/AddUserForm.vue";

export default {
  name: "App",
  components: {
    UserTable,
    AddUserForm,
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
