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
    <div id="section">
        <div class="row align-items-center">
            <div class="col">
                <div class="container">
                    <h1>{{ Title }}</h1>
                    <p>
                        {{ Paragraph }}
                    </p>
                </div>
            </div>
            <div class="col">
                <img id="Image" v-bind:src="Pic">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        Title: String,
        Paragraph: String,
        Pic: String
    }
}
</script>