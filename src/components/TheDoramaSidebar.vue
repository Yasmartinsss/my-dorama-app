<template>
  <div class="sidebar">
    <ul>
      <li><a href="https://www.maioresemelhores.com/melhores-doramas/">Popular Doramas</a></li>
      <li><a href="https://br.mydramalist.com/shows/newest">New Releases</a></li>
      <li><a href="https://br.mydramalist.com/shows/top_korean_dramas">Top Rated</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'DoramaSidebar',
};
</script>

<style scoped>
.sidebar {
  background-color: #f9f9f9;
  padding: 20px;
  width: 200px;
}
.sidebar ul {
  list-style: none;
  padding: 0;
}
.sidebar li {
  margin-bottom: 10px;
}
.sidebar a {
  text-decoration: none;
  color: #333;
}
.sidebar a:hover {
  color: #007bff;
}
</style>
