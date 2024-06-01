<!-- src/components/DoramaAppFooter.vue -->
<!-- src/components/DoramaAppFooter.vue -->
<template>
  <footer class="footer">
    <div class="footer-content">
      <p>&copy; 2024 Meu Aplicativo de Doramas. Todos os direitos reservados.</p>
      <!-- Mostrar mensagem de envio do formulário -->
      <p v-if="formSubmitted" class="success-message">Formulário enviado com sucesso!</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'DoramaAppFooter',
  data() {
    return {
      formSubmitted: false
    };
  }
};
</script>

<style scoped>
.footer {
  background-color: #42b983;
  color: white;
  text-align: center;
  padding: 20px;
  position: fixed;
  width: 100%;
  bottom: 0;
}

.footer-content {
  max-width: 1200px; /* Ajuste conforme necessário */
  margin: 0 auto;
}

.success-message {
  color: #4caf50; /* Cor verde para indicar sucesso */
  font-weight: bold;
}
</style>
