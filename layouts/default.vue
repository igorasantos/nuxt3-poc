<template>
  <div>
    <header>
      <nav>
        <ul>
          <li><NuxtLink to="/">Home</NuxtLink></li>
          <li><NuxtLink to="/about">About</NuxtLink></li>
          <li><NuxtLink to="/top/nested/hash1">Hash1 Dynamic</NuxtLink></li>
          <li><NuxtLink to="/top/nested/132112312">Hash number Dynamic</NuxtLink></li>
          <li><NuxtLink to="/top/nested/12345678912345678901">Hash 20 numbers Dynamic</NuxtLink></li>
          <li><NuxtLink to="/top/nested/asd123sdd213213sdfse">Hash 20 chars Dynamic</NuxtLink></li>
        </ul>
      </nav>
    </header>
    <slot />
  </div>
</template>