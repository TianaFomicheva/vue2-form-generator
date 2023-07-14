<template>
  <div>
    <div class="row">
      <div class="label">{{ label }}</div>
      <div class="field">
        <select v-model="proxyValue">
          <option value="1">1</option>
          <option value="2">2</option>
          <option value="3">3</option>
        </select>
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