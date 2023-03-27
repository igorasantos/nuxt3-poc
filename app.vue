<template>
  <div>
    <header>
      <nav>
        <ul>
          <li><NuxtLink to="/">Home</NuxtLink></li>
          <li><NuxtLink to="/about">About</NuxtLink></li>
          <li><NuxtLink to="/top/nested/hash1">Hash1 Dynamic</NuxtLink></li>          
          <li><NuxtLink to="/top/nested/132112312">Hash number Dynamic</NuxtLink></li>          
        </ul>
      </nav>
    </header>
    <NuxtPage />
  </div>
</template>
<script lang="ts" setup>
useHead({
  titleTemplate: (pageTitle) => {
    return pageTitle ? `Acme PDFs - ${pageTitle}` : 'Acme PDFs';
  }
})
</script>