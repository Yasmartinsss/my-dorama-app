<!-- src/components/TheDoramaList.vue -->
<!-- src/components/TheDoramaList.vue -->
<template>
  <div class="dorama-list">
    <h2>Lista de Doramas</h2>
    <ul>
      <li v-for="(dorama, index) in doramas" :key="dorama.id">
        <div class="dorama-info">
          <img :src="dorama.image" alt="Imagem do Dorama" class="dorama-image">
          <div class="dorama-details">
            <h3>{{ dorama.title }}</h3>
            <p>{{ dorama.description }}</p>
          </div>
        </div>
        <button @click="editDorama(index)">Editar</button>
        <button @click="removeDorama(index)">Remover</button>
        <button @click="toggleFavorite(index)">
          {{ dorama.favorite ? 'Remover dos Favoritos' : 'Adicionar aos Favoritos' }}
        </button>
      </li>
    </ul>
    <div class="new-dorama">
      <input v-model="newDoramaTitle" placeholder="Adicionar novo dorama" @keyup.enter="addDorama">
      <input v-model="newDoramaImage" placeholder="URL da imagem" @keyup.enter="addDorama">
      <button @click="addDorama">Adicionar</button>
    </div>
    <div v-if="editIndex !== null" class="edit-dorama">
      <h3>Editando: {{ doramas[editIndex].title }}</h3>
      <input v-model="editDoramaTitle" placeholder="Editar título" @keyup.enter="saveDorama">
      <input v-model="editDoramaImage" placeholder="Editar URL da imagem" @keyup.enter="saveDorama">
      <button @click="saveDorama">Salvar</button>
      <button @click="cancelEdit">Cancelar</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TheDoramaList',
  data() {
    return {
      doramas: [
        { id: 1, title: 'Lovelly Runner', description: 'Im Sol está arrasada com a morte repentina e trágica de seu astro favorito, Ryu Sun Jae, um ex-nadador que se tornou um ídolo do K-pop. Mas, em meio à sua angústia, ela magicamente volta para 2008, quando Sun Jae ainda tinha apenas 19 anos de idade! Encantada por ter a chance de ajudá-lo a evitar seu destino infeliz, Sol assume a missão de mudar o futuro... e talvez encontrar o amor no caminho. Será que seus esforços para desviar o curso do passado serão bem-sucedidos ou poderão ter consequências inesperadas?', image: 'https://th.bing.com/th/id/OIP.4gYzuJ49Bwfey4B2pZ9w7QAAAA?rs=1&pid=ImgDetMain', favorite: false },
        { id: 2, title: 'Goblin', description: 'Kim Shin é um condecorado general militar da Dinastia Goryeo que acaba traído pelo rei invejoso a quem servia. Quando Kim Shin é confrontado com a morte em vez da honra após uma grande batalha, Deus transforma Kim Shin em um duende cuja função é proteger certas pessoas de uma vida de sofrimento.', image: 'https://th.bing.com/th/id/OIP.2jOUPv6l9fuXUEROOITDqgHaK4?rs=1&pid=ImgDetMain', favorite: false },
        { id: 3, title: 'Crash Landing on You', description: 'Uma herdeira sul-coreana, Yoon Se-ri, faz um pouso forçado na Coreia do Norte durante um voo de parapente e encontra Ri Jeong-hyeok, um oficial do exército norte-coreano. Eles começam a se apaixonar, desafiando as fronteiras entre seus países.', image: 'https://referencianerd.com/wp-content/uploads/2020/12/crash-landing-on-you-featured-image-scaled-1200x720-1.jpg', favorite: false },
        { id: 4, title: 'Descendants of the Sun', description: 'A história segue um capitão das forças especiais, Yoo Si-jin, que se apaixona pela cirurgiã Kang Mo-yeon enquanto estão em uma missão de paz em um país fictício devastado pela guerra.', image: 'https://th.bing.com/th/id/OIP.wLY3PcUj6HkNm65mrRWmXAHaEK?rs=1&pid=ImgDetMain', favorite: false },
        { id: 5, title: 'My Love from the Star', description: 'Um alienígena que chegou à Terra há 400 anos, Do Min-joon, encontra uma atriz de top, Cheon Song-yi, e se apaixona por ela, enquanto se prepara para deixar o planeta.', image: 'https://th.bing.com/th/id/R.566b323a444db91d1228e341cf18a3b6?rik=4hmnRetvbFS4Dg&pid=ImgRaw&r=0', favorite: false }
      ],
      newDoramaTitle: '',
      newDoramaImage: '',
      editIndex: null,
      editDoramaTitle: '',
      editDoramaImage: ''
    };
  },
  methods: {
    addDorama() {
      if (this.newDoramaTitle && this.newDoramaImage) {
        this.doramas.push({
          id: this.doramas.length + 1,
          title: this.newDoramaTitle,
          description: 'Descrição do Novo Dorama',
          image: this.newDoramaImage,
          favorite: false
        });
        this.newDoramaTitle = '';
        this.newDoramaImage = '';
      }
    },
    removeDorama(index) {
      this.doramas.splice(index, 1);
    },
    editDorama(index) {
      this.editIndex = index;
      this.editDoramaTitle = this.doramas[index].title;
      this.editDoramaImage = this.doramas[index].image;
    },
    saveDorama() {
      if (this.editDoramaTitle && this.editDoramaImage) {
        this.doramas[this.editIndex].title = this.editDoramaTitle;
        this.doramas[this.editIndex].image = this.editDoramaImage;
        this.cancelEdit();
      }
    },
    cancelEdit() {
      this.editIndex = null;
      this.editDoramaTitle = '';
      this.editDoramaImage = '';
    },
    toggleFavorite(index) {
      this.doramas[index].favorite = !this.doramas[index].favorite;
    }
  }
};
</script>

<style scoped>
.dorama-list {
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #f9f9f9;
}
.dorama-list h2 {
  margin-bottom: 20px;
}
.dorama-list ul {
  list-style: none;
  padding: 0;
}
.dorama-list li {
  margin-bottom: 20px;
}
.dorama-info {
  display: flex;
}
.dorama-image {
  width: 100px;
  height: auto;
  margin-right: 20px;
}
.dorama-details {
  flex: 1;
}
.dorama-details h3 {
  margin-bottom: 5px;
}
.dorama-details p {
  margin: 0;
}
.new-dorama,
.edit-dorama {
  margin-top: 20px;
}
</style>
