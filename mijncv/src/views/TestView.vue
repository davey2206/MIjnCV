<template>
  <div class="Test">
    <NavBar></NavBar>
    <LayoutMain></LayoutMain>
  </div>
</template>

<script>
// @ is an alias to /src
import NavBar from '@/components/NavBar.vue';
import LayoutMain from '@/components/LayoutMain.vue';

export default {
  name: 'HomeView',
  components: {
    NavBar,
    LayoutMain
  }
}
</script>
