 <!-- eslint-disable -->
<template>
  <div class="hello">
    <ckeditor :editor="editor" v-model="editorData" :config="editorConfig"></ckeditor>
  </div>
</template>

<script>
/* eslint-disable */
import Editor from 'ckeditor5-custom-build/build/ckeditor';
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return {
      editor: Editor,
      editorData: '<p>First paragraph</p><div class="testing">Second div with class<span> updated</span></div>',
      editorConfig: {
          // The configuration of the editor.
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.testing{
  background-color: red;
  color:#fff;
}
</style>
