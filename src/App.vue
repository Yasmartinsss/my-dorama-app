<!-- src/App.vue -->
<!-- src/App.vue -->
<template>
  <div id="app">
    <DoramaAppHeader />
    <div class="main-content">
      <TheDoramaSidebar />
      <div class="content">
        <HelloWorld msg="Bem-vindo ao Dorama World!" />
        <TheDoramaList />
        <DoramaContactForm />
      </div>
    </div>
    <DoramaAppFooter />
  </div>
</template>

<script>
import DoramaAppHeader from './components/DoramaAppHeader.vue';
import TheDoramaList from './components/TheDoramaList.vue';
import DoramaContactForm from './components/DoramaContactForm.vue';
import TheDoramaSidebar from './components/TheDoramaSidebar.vue';
import DoramaAppFooter from './components/DoramaAppFooter.vue';
import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'App',
  components: {
    DoramaAppHeader,
    TheDoramaSidebar,
    TheDoramaList,
    DoramaContactForm,
    DoramaAppFooter,
    HelloWorld
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.main-content {
  display: flex;
  flex-grow: 1;
  margin-bottom: 80px; /* Ajuste conforme necessário para garantir que o conteúdo não seja coberto pelo rodapé */
}

.sidebar {
  width: 200px;
}

.content {
  flex-grow: 1;
  padding: 20px;
}

.footer {
  width: 100%;
  position: fixed;
  bottom: 0;
}
</style>
