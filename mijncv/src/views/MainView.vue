<template>
  <div class="Test">
    <section v-if="loading">
      <h1> loading.....</h1>
    </section>
    <section v-else>
      <NavBar></NavBar>
      <div v-for="Page in Pages">
        <h1 style="margin-top: 52px;">{{Page.name}}</h1>
        <div v-for="Section in Sections">
          <div v-if="Page.id == Section.pageID">
            <div v-if="Section.layout == 1">
              <LayoutMain :ID="Section.id" Pic="https://cdn.discordapp.com/attachments/438780813807714304/1039513899537547264/unknown.png"></LayoutMain>
            </div>
            <div v-if="Section.layout == 2">
              <LayoutMainAlt :ID="Section.id" Pic="https://cdn.discordapp.com/attachments/438780813807714304/1039513899537547264/unknown.png"></LayoutMainAlt>
            </div>
          </div>
        </div>
      </div>
      {{ $route.params.Id}}
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
        Sections: null,
        Pages: null,
        loading: true
        }
    },
    mounted(){
        axios.get("https://localhost:7059/api/Sections").then(response => (this.Sections = response.data)).finally(() => this.loading = false),
        axios.get("https://localhost:7059/api/Pages").then(response => (this.Pages = response.data)).finally(() => this.loading = false)
    }
}
</script>
