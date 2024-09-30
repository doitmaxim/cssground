<script setup lang="ts">

</script>

<template>
  <Toolbar>
    <template #start>
      <b>
        cssground
      </b>
    </template>

    <template #center>
      <Button as="router-link" label="home" to="/" link />
      <Button as="router-link" label="games" to="/games" link />
    </template>

    <template #end>
      <Button label="sign in" />
    </template>

  </Toolbar>
</template>

<style scoped>

</style>