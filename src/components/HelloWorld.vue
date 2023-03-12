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
      editorData: `<p>First paragraph</p>
      <div class="testing">Second div with class<span> updated</span>
        </div>
        <ol class="order-list"><li>first</li><li>second</li></ol>
        `
        ,
      editorConfig: {
          // The configuration of the editor.
          htmlSupport: {
          allow: [
            {
              name: 'div',
              classes: true
            },
            {
              name: 'span',
              classes: true
            },
            {
              name: 'li',
              classes: true
            },
            {
              name: 'ol',
              classes: true
            }
          ]
      }
    }
  }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
h3 {
  margin: 40px 0 0;
}

a {
  color: #42b983;
}
.testing{
  background-color: red;
  color:#fff;
}
.order-list{
  display: flex;
}
</style>
