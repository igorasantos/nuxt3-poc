<template>
  <NuxtLayout>
    <NuxtPage/>
  </NuxtLayout>
</template>
<script lang="ts" setup>
useHead({
  titleTemplate: (pageTitle) => {
    return pageTitle ? `Acme PDFs - ${pageTitle}` : 'Acme PDFs';
  }
})
</script>