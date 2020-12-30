<template>
  <v-app>
    <title-bar></title-bar>
    <v-main>
      <HelloWorld />
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import TitleBar from "@/components/TitleBar/TitleBar";
export default {
  name: 'App',

  components: {
    TitleBar,
    HelloWorld
  },

  data: () => ({
    //
  }),
}
</script>
