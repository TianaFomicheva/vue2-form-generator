<template>
  <div>
    <div class="row">
      <div class="label">{{ label }}</div>
      <div class="field">
        <textarea v-model="proxyValue" ></textarea>
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["label", "value"],
  computed: {
    proxyValue: {
      get() {
        return this.value;
      },
      set(newValue) {
        this.$emit("input", newValue);
      },
    },
  },
};
</script>

<style>
</style>