<template>
  <div id="app">
    <div class="container">
      <div class="header">
        <schema-generator @add-field="addField" />
      </div>
      <div class="fields">
        <form-generator :schema="fields" />
      </div>
    </div>
  </div>
</template>

<script>
import SchemaGenerator from "./components/schemaGenerator.vue";
import FormGenerator from "./components/formGenerator.vue";

export default {
  name: "App",
  components: {
    SchemaGenerator,
    FormGenerator,
  },
  data() {
    return {
      schema: [],
    };
  },
  computed: {
    fields() {
      return this.schema;
    },
  },

  methods: {
    addField(field) {
      this.schema.push(field);

    },
    clearGeneratorField(){
      
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
