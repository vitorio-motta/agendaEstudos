<script setup>
const nome = "Vitório Motta";
</script>

<template>
  <section>
    <h1>Agenda de Estudos</h1>
    <p><strong>{{ nome }}</strong></p>
    <p>
      meu projeto vue.js, organizador de tarefas.
    </p>
    <RouterLink to="/tarefas">ir para minhas tarefas</RouterLink>
  </section>
</template>