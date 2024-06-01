<!-- src/components/DoramaContactForm.vue -->
<!-- src/components/DoramaContactForm.vue -->
<template>
    <div class="contact-form">
      <h2>Formulário de Contato</h2>
      <form @submit.prevent="submitForm">
        <label for="name">Nome:</label>
        <input type="text" id="name" v-model="formData.name">
  
        <label for="email">E-mail:</label>
        <input type="email" id="email" v-model="formData.email">
  
        <label for="message">Mensagem:</label>
        <textarea id="message" v-model="formData.message"></textarea>
  
        <button type="submit">Enviar</button>
      </form>
      <div v-if="submitted">
        <h3>Formulário enviado com sucesso!</h3>
        <p>Nome: {{ formData.name }}</p>
        <p>E-mail: {{ formData.email }}</p>
        <p>Mensagem: {{ formData.message }}</p>
        <button @click="resetForm">Novo Formulário</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'DoramaContactForm',
    data() {
      return {
        formData: {
          name: '',
          email: '',
          message: ''
        },
        submitted: false
      };
    },
    methods: {
      submitForm() {
        this.submitted = true;
        console.log('Formulário enviado!', this.formData);
      },
      resetForm() {
        this.formData.name = '';
        this.formData.email = '';
        this.formData.message = '';
        this.submitted = false;
      }
    }
  };
  </script>
  
  <style scoped>
  .contact-form {
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
  </style>
  