<template>
  <div class="row">
    <div class="column">
      <h1>
        List of users
        <span class="tiny-text">{{ userTotalCount }} User in the list</span>
      </h1>
    </div>
    <div class="column column-30 column-offset-25">
      <form>
        <label for="user-search">Search by name</label>
        <input type="text" id="user-search" v-model="searchQuery" />
      </form>
    </div>
  </div>
  <div class="row">
    <div class="column">
      <table>
        <thead>
          <tr>
            <th>Name</th>
            <th>Age</th>
            <th>hometown</th>
            <th></th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(user, index) in filteredUsers" v-bind:key="index">
            <td>{{ user.name }}</td>
            <td>{{ user.age }}</td>
            <td>{{ user.hometown }}</td>
            <td class="text-right">
              <BaseButton variant="outline" @button-click="handleButtonClick"
                >Delete</BaseButton
              >
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import BaseButton from "./BaseButton.vue";

export default {
  name: "UserTable",
  components: {
    BaseButton,
  },
  data() {
    return {
      searchQuery: "",
      users: [
        {
          name: "Joe",
          age: 37,
          hometown: "Lüneburg",
        },
        {
          name: "Franz",
          age: 25,
          hometown: "Berlin",
        },
        {
          name: "Norbert",
          age: 42,
          hometown: "Hannover",
        },
        {
          name: "Sven",
          age: 47,
          hometown: "München",
        },
      ],
    };
  },
  computed: {
    filteredUsers() {
      return this.users.filter((user) =>
        user.name.toLowerCase().startsWith(this.searchQuery.toLowerCase())
      );
    },
    userTotalCount() {
      return this.filteredUsers.length;
    },
  },
  methods: {
    handleButtonClick() {
      console.log("Button was clicked");
    },
  },
};
</script>
