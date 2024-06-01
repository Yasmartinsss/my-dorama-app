<!-- src/components/HelloWorld.vue -->
<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      Bem-vindo ao aplicativo Dorama World! Aqui você encontra informações e listas dos melhores doramas.
    </p>
    <h3>Funcionalidades Principais</h3>
    <ul>
      <li>Lista de Doramas</li>
      <li>Formulário de Contato</li>
      <li>Recomendações de Doramas Populares</li>
    </ul>
    <h3>Links Úteis</h3>
    <ul>
      <li><a href="https://vuejs.org" target="_blank" rel="noopener">Documentação do Vue.js</a></li>
      <li><a href="https://br.mydramalist.com" target="_blank" rel="noopener">MyDramaList</a></li>
      <li><a href="https://www.netflix.com" target="_blank" rel="noopener">Netflix</a></li>
      <li><a href="https://www.viki.com" target="_blank" rel="noopener">Viki</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin: 0 10px;
}
a {
  color: #9742b9;
}
</style>
