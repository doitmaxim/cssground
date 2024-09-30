<script setup lang="ts">
// import hljs from 'highlight.js';
import CodeEditor from 'simple-code-editor';

const value = defineModel<string>({default: ''});
</script>

<template>
  <code-editor v-model="value" :languages="[['css', 'C ASS ASS']]" theme="atom-one-dark" line-nums> </code-editor>
</template>
