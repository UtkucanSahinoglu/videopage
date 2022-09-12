<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" app clipped floating temporary>
      <v-list dense>
        <v-row class="ma-2 mb-3">
          <v-icon class="mx-4" large>mdi-video</v-icon>
          <v-toolbar-tittle class="align-center">
            <span class="tittle">VideoPage</span>
          </v-toolbar-tittle>
        </v-row>
        <v-list-item v-for="item in items" :key="item.icon" link>
          <v-list-item-action>
            <v-icon>
              {{ item.icon }}
            </v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>
              {{ item.text }}
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar app clipped-left>
      <v-app-bar-nav-icon @click="drawer = !drawer" />
      <v-icon class="mx-4" large>mdi-video</v-icon>
      <v-toolbar-tittle class="align-center">
        <span class="tittle">VideoPage</span>
      </v-toolbar-tittle>
      <v-spacer />
      <v-text-field
        class="mt-7"
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
      <div>
        <v-menu
          v-model="menu"
          :close-on-content-click="false"
          :nudge-width="250"
          offset-x
        >
          <template v-slot:activator="{ on }">
            <v-avatar size="40">
              <img
                v-on="on"
                src="https://pbs.twimg.com/media/Ez6K7yJX0AwxKIQ?format=jpg&name=medium"
              />
            </v-avatar>
          </template>

          <v-card>
            <v-list>
              <v-list-item>
                <v-list-item-avatar> </v-list-item-avatar>
                <v-list-item-content>
                  <v-list-item-title>Utkucan Sahinoglu</v-list-item-title>
                  <v-list-item-subtittle>VideoPage</v-list-item-subtittle>
                </v-list-item-content>
              </v-list-item>
            </v-list>
            <v-divider />
            <v-list>
              <v-list-item>
                <v-list-item-action>
                  <v-icon>mdi-cog</v-icon>
                </v-list-item-action>
                <v-list-item-tittle>Ayarlar</v-list-item-tittle>
              </v-list-item>
            </v-list>
            <v-list>
              <v-list-item>
                <v-list-item-action>
                  <v-switch v-model="theme" color="green" />
                </v-list-item-action>
                <v-list-item-tittle>Karanlik Tema</v-list-item-tittle>
              </v-list-item>
            </v-list>
            <v-card-action>
              <v-spacer />
              <v-btn color="primary" text @click="menu = false">
                Cikis yap
              </v-btn>
            </v-card-action>
          </v-card>
        </v-menu>
      </div>
    </v-app-bar>
    <v-content>
      <v-container>
        <v-row class="mb-4">
          <v-col
            sm="6"
            md="4"
            lg="3"
            xl="2"
            v-for="(item, index) in 200"
            :key="index"
          >
            <v-card>
              <v-img
                height="200px"
                :src="`https://picsum.photos/300/200?image=${index + 1}`"
                :lazy-src="`https://picsum.photos/10/6?image=${index + 1}`"
              />
              <v-card-subtitle class="">Number {{ item }}</v-card-subtitle>
              <v-card-text class="text--primary">
                <div>Baslik Alani</div>
                <div>Baslik Icerigi</div>
              </v-card-text>
              <v-card-actions>
                <v-btn color="orange" text>Kaydet</v-btn>
                <v-btn color="orange" text>Paylas</v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    items: [
      { icon: "mdi-trending-up", text: "Populer Icerik" },
      { icon: "mdi-youtube-subscription", text: "Takip" },
      { icon: "mdi-history", text: "Gecmis" },
      { icon: "mdi-playlist-play", text: "Oynatma Listesi" },
      { icon: "mdi-clock", text: "Videolarimiz" },
    ],

    menu: false,
    theme: false,
    drawer: false,
  }),
  watch: {
    theme: function (next) {
      this.$vuetify.theme.dark = next;
    },
  },
};
</script>
