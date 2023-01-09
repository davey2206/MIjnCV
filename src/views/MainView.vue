<template>
  <div class="Test">
    <section v-if="loading">
      <h1>{{ $route.params.id }} loading.....</h1>
    </section>
    <section v-else>
      <NavBar :ID="CV" :Pages="Pages"></NavBar>
      <div v-for="Page in Pages">
        <div :id="Page.name">
          <h1 style="margin-top: 52px;">{{Page.name}}</h1>
          <div v-for="Section in Sections">
            <div v-if="Page.id == Section.pageID">
              <div v-if="Section.layout == 1">
                <LayoutMain :ID="Section.id" :Pic="Section.image"></LayoutMain>
              </div>
              <div v-if="Section.layout == 2">
                <LayoutMainAlt :ID="Section.id" :Pic="Section.image"></LayoutMainAlt>
              </div>
            </div>
          </div>
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
  created() {
   this.CV = this.$route.params.Id; 
  },
  data () {
        return {
        Sections: null,
        Pages: null,
        loading: true,
        CV: null
        }
    },
    mounted(){
        axios.get("https://localhost:7059/api/Sections/CV/" + this.CV).then(response => (this.Sections = response.data)).finally(() => this.loading = false),
        axios.get("https://localhost:7059/api/Pages/CV/" + this.CV).then(response => (this.Pages = response.data)).finally(() => this.loading = false)
    }
}
</script>
