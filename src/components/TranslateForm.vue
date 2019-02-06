<template>
  <div id="translateForm">TRANSLATE FORM
    <form v-on:submit="formSubmit">
      <!-- binds this input to a component property -->
      <input type="text" v-model="textToTranslate" placeholder="Enter a Word...">
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
      textToTranslate: ""
    };
  },
  methods: {
    // prevent from submitting to a webpage
    formSubmit(e) {
      // test- alert("Translated Word submitted");
      // emitting the textToTranslate value to App.vue
      this.$emit("formSubmit", this.textToTranslate);
      e.preventDefault();
    }
  }
};
</script>

<style>
</style>
