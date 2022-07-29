<template lang="">
    <div>
        
        <HeaderComponent />

            <main class="d-flex flex-fill mb-5" id="main">
                <div class="container-lg d-flex">
                    <div class="row">
                        <div class="col mb-5">

                            <BreadcrumbComponent />

                            <div class="main-content pl-sm-3 mt-4" id="main-content">
                                <article>
                                        <div class="p-3">
                                            <p><h1>{{noticias.attributes.Titulo}}</h1></p>
                                            <span class="br-divider my-3"></span>
                                            <p>Publicado em </p>
                                        </div>
                                    
                                </article>
                            </div>
                        </div>
                    </div>
                </div>
            </main>


        <FooterComponent />
        
    </div>
</template>


<script>
import HeaderComponent from '/components/header/HeaderComponent.vue';
import FooterComponent from '/components/footer/FooterComponent.vue';

import BreadcrumbComponent from "/components/content/items/BreadcrumbComponent.vue";
export default {

    components: { HeaderComponent, FooterComponent, BreadcrumbComponent },
    async asyncData({ params }) {
        const noticias = await fetch(
            'http://200.18.165.172:1337/api/noticias/' + params.article
        )
            .then((response) => response.json())
            .then((res) => res.data)
        return { noticias }
    },
}

</script>