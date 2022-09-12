<template>
  <v-app>
    <v-app-bar app clipped-left>
      <v-app-bar-nav-icon />
      <v-icon class="mx-4" large>mdi-video</v-icon>
      <v-toolbar-tittle class="align-center">
        <span class="tittle">VideoPage</span>
      </v-toolbar-tittle>
      <v-spacer />
      <v-text-field
        solo
        placeholder="Ara...."
        single-line
        append-icon="mdi-magnify"
        color="white"
      />
      <v-spacer />
      <v-btn class="m1-0" icon>
        <v-icon>mdi-apps</v-icon>
      </v-btn>
      <v-btn class="ma-2" icon>
        <v-icon>mdi-bell</v-icon>
      </v-btn>
    </v-app-bar>
    <div>test</div>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
  }),
};
</script>
