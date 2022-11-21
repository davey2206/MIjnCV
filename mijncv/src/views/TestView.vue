<template>
  <div class="Test">
    <section v-if="loading">
      <h1> loading.....</h1>
    </section>
    <section v-else>
      <NavBar></NavBar>
      <div v-for="Test in Tests">
        <div v-if="Test.layout == 1">
          <LayoutMain :ID="Test.id" Pic="https://cdn.discordapp.com/attachments/438780813807714304/1039513899537547264/unknown.png"></LayoutMain>
        </div>
        <div v-if="Test.layout == 2">
          <LayoutMainAlt :ID="Test.id" Pic="https://cdn.discordapp.com/attachments/438780813807714304/1039513899537547264/unknown.png"></LayoutMainAlt>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
import NavBar from '@/components/NavBar.vue';
import LayoutMain from '@/components/LayoutMain.vue';
import LayoutMainAlt from '@/components/LayoutMainAlt.vue';
import axios from 'axios';

export default {
  name: 'HomeView',
  components: {
    NavBar,
    LayoutMain,
    LayoutMainAlt
  },
  data () {
        return {
        Tests: null,
        loading: true
        }
    },
    mounted(){
        axios.get("https://localhost:7059/api/Sections").then(response => (this.Tests = response.data)).finally(() => this.loading = false)
    }
}
</script>
