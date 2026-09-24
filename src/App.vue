<template>
  <main class="container">
    <RouterView />
  </main>
</template>

<style>
body {
  margin: 0;
  font-family: system-ui, sans-serif;
  background: #f7f4ee; /* Bege/Creme suave */
  color: #3d352e;      /* Marrom escuro profundo */
}

.container {
  max-width: 560px;
  margin: 48px auto;
  padding: 0 20px;
}

h1 {
  margin-bottom: 8px;
}

a {
  color: #a67c52;             /* Caramelo terroso */
  text-decoration: none;
  padding: 12px;
  border: 1px solid #a67c52;
  border-radius: 16px;
  transition: ease-out 250ms;
}

a:hover {
  background-color: #a67c52;
  color: #f7f4ee;            /* Cor do fundo para contraste no hover */
}
</style>