<template>
  <div id="translateForm">TRANSLATE FORM
    <form v-on:submit="formSubmit">
      <!-- binds this input to a component property -->
      <input type="text" v-model="textToTranslate" placeholder="Enter a Word...">
      <select v-model="language">
        <option value="ru">Russian</option>
        <option value="es">Spanish</option>
        <option value="fr">French</option>
        <option value="zh">Chinese</option>
      </select>
      <input type="submit" value="Translate">
    </form>
  </div>
</template>

<script>
export default {
  name: "TranslateForm",
  data() {
    return {
      // we're binding our input text above to this method
      textToTranslate: "",
      language: ""
    };
  },
  created() {
    this.language = "ru";
  },
  methods: {
    // prevent from submitting to a webpage
    formSubmit(e) {
      // test- alert("Translated Word submitted");
      // emitting the textToTranslate value to App.vue
      this.$emit("formSubmit", this.textToTranslate, this.language);
      e.preventDefault();
    }
  }
};
</script>

<style>
</style>
