<template>
  <v-app>
    <navbar></navbar>
    <!-- root element Start-->
    <v-content>
      <!-- page Content Holder Start-->
      <router-view></router-view>
      <!-- page Content Holder End-->
    </v-content>
    <!-- root element End-->
  </v-app>
</template>

<script>
import Navbar from '@/components/Navbar'
export default {
  name: 'App',

  components: {
    Navbar,
  },

  data: () => ({
    //
  }),
}
</script>
