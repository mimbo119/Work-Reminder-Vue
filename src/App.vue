<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>To DO List</span>
      </v-toolbar-title>
      <!-- <v-spacer></v-spacer> -->
    </v-app-bar>

    <v-content>
      <ToDo/>
    </v-content>
  </v-app>
</template>

<script>
import ToDo from './components/ToDo';

export default {
  name: 'App',
  components: {
    ToDo,
  },
  data: () => ({
    //
  }),
};
</script>
