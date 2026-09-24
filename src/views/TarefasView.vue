<script setup>
import { ref } from "vue";

const novaTarefa = ref("");
const tarefas = ref([]);
let proximoId = 1;

function adicionar() {
  const texto = novaTarefa.value.trim();
  if (texto === "") return;

  tarefas.value.push({ id: proximoId++, texto });
  novaTarefa.value = "";
}
</script>

<template>
  <section>
    <h1>Minhas tarefas</h1>

    <div class="form">
      <input
        v-model.trim="novaTarefa"
        type="text"
        placeholder="Digite uma tarefa"
        @keyup.enter="adicionar"
      />
      <button @click="adicionar">Adicionar</button>
    </div>

    <ul>
      <li v-for="tarefa in tarefas" :key="tarefa.id">
        {{ tarefa.texto }}
      </li>
    </ul>

    <p v-if="tarefas.length === 0">Nenhuma tarefa ainda.</p>

    <RouterLink to="/">Voltar para o início</RouterLink>
  </section>
</template>

<style scoped>
.form {
  display: flex;
  gap: 8px;
  margin: 16px 0;
}

input {
  flex: 1;
  padding: 8px 12px;
  border: 1px solid var(--border, #e3ded5);
  border-radius: 6px;
  font-size: 1rem;
  background-color: var(--bg, #f7f4ee);
  color: var(--text-h, #3d352e);
  outline: none;
  transition: border-color 0.2s, box-shadow 0.2s;
}

input:focus {
  border-color: var(--accent, #c49a6c);
  box-shadow: 0 0 0 3px rgba(196, 154, 108, 0.2);
}

button {
  padding: 8px 16px;
  border: none;
  border-radius: 6px;
  background: #c49a6c;   /* Bege dourado/terracota suave */
  color: #ffffff;
  font-size: 1rem;
  font-weight: 500;
  cursor: pointer;
  transition: background-color 0.2s;
}

button:hover {
  background: #b0875b;   /* Bege ligeiramente mais escuro ao passar o mouse */
}

ul {
  padding-left: 20px;
}

li {
  margin-bottom: 6px;
  color: var(--text-h, #3d352e);
}

a {
  color: #a67c52;        /* Tom caramelo para links */
  text-decoration: none;
  transition: color 0.2s;
}

a:hover {
  color: #8a643f;
}
</style>