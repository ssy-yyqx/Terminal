<template>
  <div>
    <editor
      ref="editor"
      :content="value"
      :theme="'crimson_editor'"
      :config="config"
      :height="50"
      @change="editorChange">
    </editor>
    <editor
      ref="editor"
      :content="value"
      :theme="'crimson_editor'"
      :config="config"
      :height="50"
      @change="editorChangeq">
    </editor>
  </div>
</template>

<script>
import Editor from './sql'
import { format } from 'sql-formatter'



export default {
  components:{Editor},
  data(){
    return {
      value:'',
      config:{font_size: 16,sql_atom: true}
    }
  },
  methods:{
    // 方法
    formatter () {
        const editor = this.$refs.editor.editor
        const content = editor.getValue()
        const formatContent = format(content)
        editor.setValue(formatContent)
    },
    editorChange(value){
      console.log(value,123);
    },
    editorChangeq(value){
      console.log(value,456);
    }
  }
}
</script>

<style>

</style>
