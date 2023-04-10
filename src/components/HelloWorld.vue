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
        }
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


.period-andList > li:nth-last-child(2)::after {
		content: '; and';
	}

	.period-andList > li:last-child::after {
		content: '.';
	}

	.period-andList > li:not(:nth-last-child(2)):not(:last-child):not(span)::after {
		content: ';';
	}


  ol.four,
	ol.eight {
		counter-reset: four;
		list-style-type: none;
	}

	ol.four > li:before,
	ol.eight > li:before {
		position: absolute;
		counter-increment: four;
		content: '(' counter(four, lower-roman) ')';

		margin-left: -2.5em;
		margin-right: 1em;
	}

  
	ol.eight {
		counter-reset: eight;
		list-style-type: none;
	}

	ol.eight > li:before {
		position: absolute;
		counter-increment: eight;
		content: '(' counter(eight, lower-alpha) ')';

		margin-left: -2.5em;
		margin-right: 1em;
	}


	
.one > li::marker,.two > li::marker,.three > li::marker,.four > li::marker,.five > li::marker,.six > li::marker,.seven > li::marker,.eight > li::marker,.nine > li::marker{
	content: '';
}

.ck-editor__editable .ck-list-bogus-paragraph{
	display: unset !important;
}

.ck-editor__editable .ck-list-bogus-paragraph:has(> br){
	display: -webkit-inline-box !important;
}

p:empty {
  display:none
}

.ck-editor__top{
	position: fixed !important;
	bottom:0 !important;
}


</style>
