<template>
    <div class="row mb-md-2">
        <div class="col-md-6 col-lg-4" v-for="index in 3 ">
            <div class="br-card  ">
                <div class="position-relative">
                    <img src="http://200.18.165.172:8080/ufcat/secretarias/seti/f91ca042-e4c4-4df5-9b53-451efebb74b1.jpeg/@@images/2e2c9978-8ecf-4f6e-a701-09430a824b93.jpeg"
                        class="card-img-top" alt="image">
                </div>
                <div class="tile-subtitle">
                    <p v-if="$fetchState.pending">Carregando notícias...</p>
                    <p v-else-if="$fetchState.error">Ocorreu um erro, reinicie a página! :(</p>
                    <div v-else>
                        <NuxtLink :to="{ 
                            path: 'noticias/'+`${mountains[index-1].id}`
                                                   }" >
                            <h5 class="font-weight-normal">
                                {{mountains[index-1].id}}
                                {{ mountains[index - 1].attributes.Titulo }}
                            </h5>
                        </NuxtLink>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>


<script>
export default {
    data() {
        return {
            mountains: [],
            titlesID: []
        }
    },
    async fetch() {
        this.mountains = await fetch(
            'http://200.18.165.172:1337/api/noticias'
        )
            .then((response) => response.json())
            .then((res) => res.data)
        if (this.mountains !== null) {
            for (let index in this.mountains) {
                this.titlesID.push(this.mountains[index].id + this.mountains[index].attributes.Titulo);
            }
        }
    },

}

</script>