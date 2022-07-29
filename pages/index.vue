<template>
  <div class="template-base">

    <head>

      <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
      <meta charset="UTF-8">
      <meta property="creator.productor"
        content="http://estruturaorganizacional.dados.gov.br/id/unidade-organizacional/226371">
    </head>
    <!-- Barra GOV-BR-->
    <div id="barra-brasil" style="background:#7F7F7F; height: 20px; padding:0 0 0 10px;display:block;">
      <ul id="menu-barra-temp" style="list-style:none;">
        <li style="display:inline; float:left;padding-right:10px; margin-right:10px; border-right:1px solid #EDEDED">
          <a href="http://brasil.gov.br" style="font-family:sans,sans-serif; text-decoration:none; color:white;">Portal
            do Governo Brasileiro</a>
        </li>
      </ul>
    </div>

    <!--
    <table class="table">
      <caption>Noticias</caption>
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">Titulo</th>
          <th scope="col">Resumo</th>
          <th scope="col">Corpo</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in noticias" :key="user.id">
          <th scope="row">{{ user.id }}</th>
          <td>{{ user.Titulo }}</td>
          <td>{{ user.Resumo }}</td>
          <td>{{ user.Corpo }}</td>
        </tr>
      </tbody>
    </table>
  -->


  <!--
    <div v-for="noticia in noticias" :key="noticia.id">
      {{ noticia.attributes.Titulo }}
    </div>
  -->

    <HeaderComponent />
    <ContentComponent />
    <FooterComponent />

  </div>
</template>

<script>
import HeaderComponent from '../components/header/HeaderComponent.vue';
import FooterComponent from '../components/footer/FooterComponent.vue';
import ContentComponent from '../components/content/ContentComponent.vue';

export default {
  name: "IndexPage",
  components: { HeaderComponent, FooterComponent, ContentComponent },
  data() {
    return {
      noticias: [],
    }
  },
  created() {
    this.noticias = this.data
    //console.log(process.env.API_URL)
  },
  methods: {
    async getUsers() {
      this.noticias = data.noticias;
    }
  },
  mounted() {
    this.getUsers();
  },
  async asyncData({ $axios }) {
    const data = await $axios.$get('/noticias')
    return (data)
  }

}
</script>

<style>
@import "https://cdn.dsgovserprodesign.estaleiro.serpro.gov.br/design-system/fonts/rawline/css/rawline.css";
@import "https://fonts.googleapis.com/css?family=Raleway:300,400,500,600,700,800,900&amp;display=swap";
@import "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.11.2/css/all.min.css";
</style>
