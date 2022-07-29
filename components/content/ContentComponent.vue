<template>
    <main class="d-flex flex-fill mb-5" id="main">
        <div class="container-lg d-flex">
            <div class="row">

                <MenuComponent />

                <div class="col mb-5">

                    <BreadcrumbComponent />

                    <div class="main-content pl-sm-3 mt-4" id="main-content">

                        <CarouselComponent />


                        <section class="pt-5 pb-5">
                            <div class="title-flex">
                                <h2>Notícias em Destaque</h2>
                            </div><!--  <span class="br-divider my-3"></span> -->

                            <NoticiasComponent />

                            <div class="container-button">
                                <button class="br-button secondary" type="button"
                                    onclick="window.location.href='seti/noticias'">Mais
                                    Notícias
                                </button>
                            </div>
                        </section>

                        <section class="pt-5 pb-5">
                            <div class="title-flex">
                                <h2>Editais</h2>
                            </div><!--  <span class="br-divider my-3"></span> -->
                            <EditaisComponent />
                            <div class="container-button">
                                <button class="br-button secondary" type="button"
                                    onclick="window.location.href='seti/noticias'">Mais
                                    Editais
                                </button>
                            </div>
                        </section>

                        <section class="pt-5 pb-5">
                            <div class="title-flex">
                                <h2>Eventos em Destaque</h2>
                            </div><!--  <span class="br-divider my-3"></span> -->

                            <EventosComponent />

                            <div class="container-button">
                                <button class="br-button secondary" type="button"
                                    onclick="window.location.href='#'">Mais
                                    Eventos
                                </button>
                            </div>

                        </section>
                        <section class="pt-5 pb-5">
                            <div class="title-flex">
                                <h2>Serviços</h2>
                            </div><!--  <span class="br-divider my-3"></span> -->

                            <ItemsComponent />

                        </section>
                    </div>

                </div>
            </div>
        </div>
    </main>

</template>

<script>
import ItemsComponent from "./items/ItemsComponent.vue"
import NoticiasComponent from "./items/NoticiasComponent.vue"
import EventosComponent from "./items/EventosComponent.vue"
import BreadcrumbComponent from "./items/BreadcrumbComponent.vue"
import CarouselComponent from "./items/CarouselComponent.vue"
import MenuComponent from "./items/MenuComponent.vue"
import EditaisComponent from "./items/EditaisComponent.vue"
export default {
    components: { ItemsComponent, NoticiasComponent, EventosComponent, BreadcrumbComponent, CarouselComponent, MenuComponent, EditaisComponent },
    data() {
    return {
      noticias: [],
    }
  },/*
  computed: {
    // readonly
    aDouble() {
      return this.a * 2
    },
    // writable
    aPlus: {
      get() {
        return this.a + 1
      },
      set(v) {
        this.a = v - 1
      }
    }
  },*/
  created() {
    this.noticias = this.data
    /*
    console.log(this.noticias)
    //console.log(this.data)
    console.log(this.aDouble) // => 2
    console.log(this.aPlus) // => 2

    this.aPlus = 3
    console.log(this.a) // => 2
    console.log(this.aDouble) // => 4*/
  },
  methods: {
    async getUsers() {
      this.noticias = data.noticias;
    }
  },
  mounted(){
        this.getUsers();
    },
  async asyncData({ $axios }) {
    const data = await $axios.$get('/noticias/1')
    return (data)
  }
}


</script>