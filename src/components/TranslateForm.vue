<template>
  <div class="container">
    <div class="row" id="translateForm">
      <!-- push our styling to the middle -->
      <div class="mx-auto">
        <form id="transForm" class="form-inline well" v-on:submit="formSubmit">
          <!-- binds this input to a component property -->
          <br>
          <br>
          <br>
          <input
            class="form-control"
            type="text"
            v-model="textToTranslate"
            placeholder="Enter a Word..."
          >
          <select class="form-control" v-model="language">
            <option value="ru">Russian</option>
            <option value="es">Spanish</option>
            <option value="fr">French</option>
            <option value="zh">Chinese</option>
          </select>
          <br>
          <input class="btn btn-success" type="submit" value="Translate">
        </form>
      </div>
    </div>
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
#transForm {
  border-radius: 1px;
  border: 1px #ccc solid;
}
</style>
