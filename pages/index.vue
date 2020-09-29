<template>
  <section class="container">
    <div>
      <div class="component-block"/>
      <b-button @click="addComponent">Add</b-button>
      <EditorCodemirror />
    </div>
  </section>
</template>

<script>
import { BButton } from 'bootstrap-vue'
import EditorCodemirror from '~/components/EditorCodeMirror.vue'
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'

export default {
  components: {
    EditorCodemirror,
    'b-button': BButton
  },
  methods: {
    addComponent(e) {
      console.log(e)
    }
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
.component-block {
  height: 20px;
  width: 100%;
  display: block;
  background-color: #fff;
}
.component-block:hover {
  background-color: #eee;
}
</style>
