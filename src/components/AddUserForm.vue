<template>
  <div class="row">
    <div class="column column-30">
      <h3>Add new User</h3>
      <form @submit.prevent>
        <div class="row">
          <div class="column column-33">
            <label for="user-name">Name</label>
            <input type="text" id="user-name" />
          </div>
          <div class="column column-33">
            <label for="user-age">Age</label>
            <input type="text" id="user-age" />
          </div>
          <div class="column column-33">
            <label for="user-hometown">Hometown</label>
            <input type="text" id="user-hometown" />
          </div>
        </div>
        <BaseButton class="float-right" @button-click="handleButtonClick"
          >Add User</BaseButton
        >
        <div class="clearfix"></div>
      </form>
      <hr />
    </div>
  </div>
</template>

<script>
import BaseButton from "./BaseButton.vue";

export default {
  components: {
    BaseButton,
  },
  methods: {
    handleButtonClick() {
      console.log("form button was clicked");
    },
  },
};
</script>
