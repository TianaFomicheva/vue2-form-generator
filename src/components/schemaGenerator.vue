<template>
  <div>
    <div class="row">
      <div class="label">Название поля</div>
      <div class="field">
        <input v-model="label" />
      </div>
    </div>
    <div class="row">
      <div class="label">Тип поля</div>
      <div class="field">
        <select v-model="type">
          <option value="Input">Input</option>
          <option value="Select">Select</option>
          <option value="Checkbox">Checkbox</option>
          <option value="Textarea">Textarea</option>
        </select>
      </div>
    </div>
    <div class="row">
      <div class="label">Кастомная надпись</div>
      <div class="field">
        <input v-model="customData" />
      </div>
    </div>
    <div class="row button">
    <button type="button" @click="add">Добавить</button>
    </div>
  </div>
</template>
    

<script>
export default {
  name: "SchemaGenerator",
  data() {
    return {
      label: "",
      type: "",
      customData: "",
    };
  },
  emits: ["add-field"],
  methods: {
    add() {
      this.$emit("add-field", {
        label: this.label,
        type: this.type,
        customData: this.customData,
        value: "",
      });
      this.label = ""
      this.type = ""
      this.customData = ""
    },
  },
};
</script>
