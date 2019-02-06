<template>
  <div id="app">
    <h1>Word Translator</h1>
    <h5>Powered by Vue.js</h5>
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
  </div>
</template>

<script>
import TranslateForm from "./components/TranslateForm";

export default {
  name: "app",
  components: {
    TranslateForm
  },
  methods: {
    translateText: function(text) {
      // test to make sure http request to Yandex API will work
      this.$http
        .get(
          "https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20181228T102133Z.f7df98ae349299f0.070d0f465b5935cfcfffdd3de5441ba16966c870&lang=ru&text=" +
            text
        )
        .then(response => {
          console.log(response.body.text[0]);
        });
    }
  }
};
</script>

<style>
#app {
}
</style>
