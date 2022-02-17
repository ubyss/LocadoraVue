<template>
  <div id="app">
    <h1>Bem vindo(a) a {{ title }}</h1>
    <h3 v-if="horas >= 9 && horas < 17" id="aberta">ABERTA</h3>
    <h3 v-else-if="horas >= 17 && horas < 18">PROXIMO A FECHAR</h3>
    <h3 v-else id="fechada">FECHADA</h3>
    <div>
      <h2>Filmes encontrados</h2>
    </div>
    <div v-bind:key="filme.id" v-for="filme in filmes">
      <img v-bind:src="filme.imagem" alt="imagem do filme" />
      <div>
        <h5>{{ filme.titulo }}</h5>
        <p v-html="filme.descricao"></p>
        <p>R$ {{ filme.valor }}</p>
        <a href="#">ALUGAR</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      title: "Locadora famnial",
      horas: new Date().getHours(),
      filmes: [
        {
          id: 1,
          titulo: "Vingadores",
          descricao: "Um <b>filme</b> de heróis",
          valor: 25,
          imagem:
            "https://ondebaixa.com/imagens/the-avengers-os-vingadores-4k-download-torrent-dublado-dual-audio-bluray-1080p-720p-4k-hd.jpg",
        },
        {
          id: 2,
          titulo: "Pantera Negra",
          descricao: "Um filme de panteras",
          valor: 35,
          imagem:
            "https://ondebaixa.com/imagens/pantera-negra-black-panther-bluray-download-torrent-2018-dublado-dual-audio-bluray-1080p-720p-4k-hd.jpg",
        },
        {
          id: 3,
          titulo: "Homem Aranha",
          descricao: "Um filme de aranha",
          valor: 20,
          imagem:
            "https://ondebaixa.com/imagens/homem-aranha-trilogia-spider-man-trilogy-download-torrent-2002-dublado-dual-audio-bluray-1080p-720p-4k-hd.jpg",
        },
        {
          id: 4,
          titulo: "Cinderela",
          descricao: "Um filme de princesa",
          valor: 40,
          imagem:
            "https://ondebaixa.com/imagens/cinderela-e-o-pri%cc%81ncipe-secreto-download-torrent-2020-dublado-dual-audio-bluray-1080p-720p-4k-hd.jpg",
        },
        {
          id: 5,
          titulo: "Titanic",
          descricao: "Um filme romântico",
          valor: 10,
          imagem:
            "https://ondebaixa.com/imagens/007-sem-tempo-para-morrer-cam-download-torrent-2021-dublado-dual-audio-bluray-1080p-720p-4k-hd.jpg",
        },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
