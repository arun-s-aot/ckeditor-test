<!-- eslint-disable -->
<template>
  <div class="hello">
    <ckeditor
      :editor="editor"
      v-model="editorData"
      :config="editorConfig"
	  @ready="editorOnReady"
	  @input="onEditorInput"
    ></ckeditor>
  </div>
</template>

<script>
/* eslint-disable */
import Editor from 'ckeditor5-custom-build/build/ckeditor'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      editor: Editor,
      editorData: `
        <ol class="eight period-andList">
            <li>First Item</li>
            <li>Second Item</li>
            <li>Third Item</li>
        </ol>
        `,
      editorConfig: {
        // The configuration of the editor.
        htmlSupport: {
          allow: [
							{
								name: 'div',
								attributes: true,
								classes: true,
								id:true
							},
							{
								name: 'span',
								attributes: true,
								classes: true
							},
							{
								name: 'p',
								attributes: true,
								classes: true
							},
							{
								name: 'li',
								attributes: true,
								classes: true
							},
							{
								name: 'ol',
								attributes: true,
								classes: true 
							},
							{
								name: 'b',
								attributes: true,
								classes: true 
							},
							{
								name: 'i'
							},
						]
        },
		exportWord:{
			stylesheets: [ 'EDITOR_STYLES','./testcss.css' ],
			fileName: 'my-document.docx'
		},
      }
    }
  },
  methods:{
	editorOnReady(editor){
		console.log('editorOnReady----->',editor)
	},
	onEditorInput(editor){
		console.log('onEditorInput==>',editor)
	},
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
@import './testcss.css';

h3 {
  margin: 40px 0 0;
}

a {
  color: #42b983;
}
.testing {
  background-color: red;
  color: #fff;
}
/* .order-list{
  display: flex;
} */




</style>
