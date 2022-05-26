<template>
  <div class="common-layout">
    <el-container>
      <el-header>fly-tools</el-header>
      <el-container>
        <el-aside width="200px">Aside</el-aside>
        <el-main>
          <codemirror
              v-model="code"
              placeholder=""
              :style="{ height: '400px' }"
              :autofocus="true"
              :indent-with-tab="true"
              :tabSize="2"
              :extensions="extensions"

          />
          <el-button @click="format()">格式化</el-button>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
import { Codemirror } from 'vue-codemirror'
import { json } from '@codemirror/lang-json'
import {ref} from "vue";

export default {
  name: 'App',
  components: {
    Codemirror
  },
  setup() {
    const code = ref(`{"id":1}`)
    const extensions = [json()]

    return {
      code,
      extensions,
      log: console.log
    }
  },
  methods:{
    format() {
      try {
        this.code = JSON.stringify(JSON.parse(this.code), null, 2)
      } catch (e) {
        console.log(e)
      }
    }
  }
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}

header, aside {
  background: black;
  color: white;
}

section.el-container {
  min-height: 900px;
}
</style>
