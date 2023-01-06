<template>
    <div class="home">
      <div>
          <h1 id="MainTitle">MijnCV</h1>
      </div>
      <div>
          <h3>Zoek een Curriculum vitea</h3>
          <form v-bind:action="Go">
              <input id="SearchBar" type="text" placeholder="Search" v-model="Go" />
              <input type="submit" hidden/>
          </form>
      </div>
    </div>
  </template>

<script>

export default {
  name: 'HomeView',
  props: {
        GoTo: null,
    },
    data(){
        return{
            Go: this.GoTo
        }
    }
}
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