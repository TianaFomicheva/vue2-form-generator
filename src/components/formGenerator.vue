<template>
  <div>
    <component
      v-for="(field, index) in schemaData"
      :key="index"
      :is="'element' + field.type"
      :label="field.label"
      v-model="field.value"
    >
    <div class="slotData">{{field.customData}}</div>
    </component>
    <div v-if="schemaData.length>0" class="row button">
    <button @click="submitData">Отправить</button>
    </div>
  </div>
</template>

<script>
import { elementInput, elementSelect, elementCheckbox, elementTextarea } from "./formElements";
export default {
  name: "FormGenerator",

  props: ["schema"],
  components: {
    elementInput,
    elementSelect,
    elementCheckbox,
    elementTextarea
  },
  computed: {
    schemaData(){
      return this.schema
    }
  },
  methods:{
      submitData(){
          console.log(this.schemaData)
      }
  }
};
</script>
