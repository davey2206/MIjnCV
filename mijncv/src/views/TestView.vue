<template>
  <div class="Test">
    <section v-if="loading">
      <h1> loading.....</h1>
    </section>
    <section v-else>
      <NavBar></NavBar>
      <LayoutMain ID="7" Pic="https://cdn.discordapp.com/attachments/438780813807714304/1039513899537547264/unknown.png"></LayoutMain>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
import NavBar from '@/components/NavBar.vue';
import LayoutMain from '@/components/LayoutMain.vue';
import axios from 'axios';

export default {
  name: 'HomeView',
  components: {
    NavBar,
    LayoutMain
  },
  data () {
        return {
        Test: null,
        loading: true
        }
    },
    mounted(){
        axios.get("https://localhost:7059/api/Sections").then(response => (this.Test = response.data)).finally(() => this.loading = false)
    }
}
</script>
