<script>
import { RouterLink, RouterView } from 'vue-router'
import Toast from 'primevue/toast';

export default {
  components: { RouterLink, RouterView, Toast }
}
</script>

<template>
  <header>
    <nav>
      <ol>
        <li><RouterLink to="/">Główna</RouterLink></li>
        <li><RouterLink to="/about">O nas</RouterLink></li>
        <li><RouterLink to="/help">Pomoc</RouterLink></li>
      </ol>
    </nav>
  </header>

  <RouterView />
  <Toast/>
</template>

<style scoped>
/* Tutaj można pisać style CSS dostępne w obrębie komponentu. */
</style>
