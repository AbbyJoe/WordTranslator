<template>
  <div class="row" id="translateForm">
      <div class="col-md-6 col-md-offset-3">
           <form id="transForm" class="well" v-on:submit="formSubmit">
                <input type="text" v-model="textToTranslate" placeholder="Enter a Word....">
                <select v-model="language">
                    <option value="ru">Russian</option>
                    <option value="es">Spanish</option>
                    <option value="fr">French</option>
                    <option value="zh">Chinese</option>
                    <option value="az">Azerbaijan</option>
                    <option value="en">English</option>
                    <option value="ar">Arabic</option>
                    <option value="nl">Dutch</option>
                    <option value="el">Greek</option>
                    <option value="he">Hebrew</option>
                    <option value="ko">Korea</option>
                    <option value="hi">Hindi</option>
                    <option value="la">Latin</option>
                    <option value="ja">Japanese</option>
                    <option value="sv">Swedish</option>
                    <option value="uk">Ukrainian</option>
                    <option value="tr">Turkey</option>
                    <option value="th">Thai</option>
                    <option value="de">German</option>
                </select>
                <input type="submit" class="btn btn-primary" value="Translate">
        </form>
      </div>
  </div>
</template>
<script>
export default {
  name: 'TranslateForm',
  data(){
      return {
          textTotranslate: '',
          language: ''
      }
  },
  created() {
      this.language = 'ru';
  },
  methods: {
      formSubmit(e) {
          this.$emit('formSubmit', this.textToTranslate, this.language)
          e.preventDefault();
      }
  }
}
</script>

<style>
input[type="text"] {
    padding: 10px;
    font-size: 17px;
    width: 400px;
}
select {
    padding: 13px;
    margin-left: 10px;
}
input[type="submit"] {
    padding: 10px;
    margin-left: 10px;
}
#transForm {
    border-radius: 10px;
    border: 1px solid #cfcfcf;
}
</style>
