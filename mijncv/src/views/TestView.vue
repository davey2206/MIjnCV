<template>
  <div class="Test">
    <NavBar></NavBar>
    <LayoutMain Title="This is a Test" Paragraph="bla bla bla bla bla bla bla bla" Pic="https://cdn.discordapp.com/attachments/438780813807714304/1039513899537547264/unknown.png"></LayoutMain>
    <LayoutMain Title="Test 2" Paragraph="blaaaaaa blaaaa blaaaaa" Pic="https://cdn.discordapp.com/attachments/1032957236617687121/1035486199734865920/unknown.png"></LayoutMain>
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
