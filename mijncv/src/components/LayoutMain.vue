<style scoped>
#section{
    padding-top: 52px;
    width: 95vw;
    height: 95vh;
    margin: 1em;
}
#Image{
    width: 80%;
}
.row{
    height: 100%;
    width: 100%;
}
</style>
<template>
    <div id="section" class="row align-items-center">
        <section v-if="loading">
            <h1> loading.....</h1>
        </section>
        <section v-else>
            {{Test}}
            <div class="row align-items-center">
                <div class="col">
                    <div class="container">
                        <h1>{{ Test.title }}</h1>
                        <p>
                            {{ Test.paragraph }}
                        </p>
                    </div>
                </div>
                <div class="col">
                    <img id="Image" v-bind:src="Pic">
                </div>
            </div>
        </section>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    props: {
        ID: null,
        Pic: String
    },
    data () {
        return {
        Test: null,
        loading: true
        }
    },
    mounted(){
        axios.get("https://localhost:7059/api/Sections/" + this.ID).then(response => (this.Test = response.data)).finally(() => this.loading = false)
    }
}
</script>