<template>
  <button v-bind:class="variantClass" v-on:click="emitButtonClick">
    <slot />
  </button>
</template>

<script>
export default {
  name: "BaseButton",
  emits: ["button-click"],
  props: {
    variant: {
      type: String,
      default: "",
    },
  },
  computed: {
    variantClass() {
      return this.variant ? `button button-${this.variant}` : "button";
    },
  },
  methods: {
    emitButtonClick() {
      this.$emit("button-click");
    },
  },
};
</script>
