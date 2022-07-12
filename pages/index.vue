<template>
  <div class="template-base">
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
  components: { HeaderComponent, FooterComponent, ContentComponent }
}
</script>

<style>
@import "https://cdn.dsgovserprodesign.estaleiro.serpro.gov.br/design-system/fonts/rawline/css/rawline.css";
@import "https://fonts.googleapis.com/css?family=Raleway:300,400,500,600,700,800,900&amp;display=swap";
@import "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.11.2/css/all.min.css";

</style>
