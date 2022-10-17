<template>
    <div>
        <h1 id="MainTitle">MijnCV</h1>
    </div>
    <div>
        <h3>Zoek een Curriculum vitea</h3>
        <input id="SearchBar" type="text" placeholder="Search" />
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'App',
    components: {

  }
});
</script>

<style>
    #app {
        font-family: Arial;
        text-align: center;
        color: white;
    }
    body{
        background-color: #303234;
    }
    #MainTitle {
        margin-top: 2em;
        font-size: 8em;
    }
    #SearchBar {
        border: none;
        border-radius: 5px;
        width: 300px;
        font-size: 20px;
    }
</style>
