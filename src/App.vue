<template>
  <div id="app" class="text-center">
    <h1>Word Translator</h1>
    <h5>Powered By Vue.js</h5>
    <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
    <TranslateOutput v-text="translatedText"></TranslateOutput>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'

export default {
  name: 'App',
  components: {
    TranslateForm,
    TranslateOutput
  },
  data: function() {
    return {
      translatedText: ''
    }
  },
  methods: {
    translateText:function(text, language) {
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20190928T201453Z.0534e39511edfdd0.8dd45a784e1f671b0990996203fc70a6f576c60e&lang='+language+'&text='+text)
    .then((response) => {
      this.translatedText = response.body.text[0]
    })    
    }
  }
}
</script>

<style>
  body {
    background: #fefefe
  }
</style>
