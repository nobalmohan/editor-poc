<template>
  <no-ssr placeholder="Codemirror Loading...">
    <codemirror
      ref="cmEditor"
      :value="code" 
      :options="cmOption"
      @ready="onCmReady"
      @focus="onCmFocus"
      @input="onCmCodeChange"
    />
  </no-ssr>
</template>
<script>
let CodeMirror = {}
let codemirror = 'div'
if (process.client || process.browser) {
  codemirror = require('./vue-codemirror').default
}
export default {
  components: {
    codemirror
  },
  data() {
    return {
      code: '',
      cmOption: {
        tabSize: 4,
        mode: 'text/javascript',
        theme: 'base16-dark',
        lineNumbers: true,
        line: true
      }
    }
  },
  mounted() {
    console.log('the current CodeMirror instance object:', this.codemirror)
    // you can use this.codemirror to do something...
  },
  methods: {
    onCmReady(cm) {
      console.log('the editor is readied!', cm)
    },
    onCmFocus(cm) {
      console.log('the editor is focused!', cm)
    },
    onCmCodeChange(newCode) {
      console.log('this is new code', newCode)
      if (process.browser) {
        this.code = newCode
      }
    }
  }
}
</script>
<style scoped>
</style>
