<script setup lang="ts">
import Editor from '@/components/Editor.vue';
import { computed, ref } from 'vue'
import axios from 'axios'

const html = ref('');
const css = ref('');

const computedHtml = computed(() => {
  return `
        <style>${css.value}</style>
        ${html.value}
      `;
})

function check() {
  axios.post('http://localhost:3000/image/check', {
      html: computedHtml.value
  })
    .then(function (response) {
      console.log(response);
    })
    .catch(function (error) {
      console.log(error);
    })
    .finally(function () {
      // выполняется всегда
    });
}
</script>

<template>
  <main class="games">

    <Button label="check" @click="check" />
    <div class="flex">
    <img src="@/assets/image.png" />

    <div class="playstage">
      <iframe :srcdoc="computedHtml" style="width: 400px; height: 400px; border: 1px solid black;"></iframe>
    </div>
    </div>

    <div class="flex">

      <editor v-model="html" />

      <editor v-model="css" />
    </div>

  </main>
</template>

<style scoped>
.games {
  padding-top: 24px;
}

.flex {
  display: flex;
  justify-content: space-around;
  margin-bottom: 32px;
}
</style>