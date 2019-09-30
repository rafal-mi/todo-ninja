<template>
  <nav>
    <v-app-bar flat app>
      <!-- <v-toolbar-side-icon></v-toolbar-side-icon> -->
      <v-app-bar-nav-icon class="grey--text" @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title class="text-uppercase grey--text">
        <span class="font-weight-light">Todo</span>
        <span>Ninja</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>

      <navigation-link :url="this.url">
        <!-- Add a Font Awesome icon -->
        <span class="fa fa-user"></span>
        Your Profile
      </navigation-link>

      <current-user :user="user"></current-user>

      <v-menu offset-y>
        <template v-slot:activator="{ on }">
          <v-btn text color="grey" dark v-on="on">Dropdown</v-btn>
        </template>
        <v-list>
          <v-list-item v-for="(item, index) in items" :key="index" @click="doNothing()">
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>

      <v-btn text color="grey">
        <span>Sign Out</span>
        <v-icon right>mdi-location-exit</v-icon>
      </v-btn>
    </v-app-bar>

    <v-navigation-drawer app v-model="drawer" class="primary">
      <!-- <v-row>
                <v-col class="text-center">
                    <v-avatar size="100" class="grey lighten-2">
                        <img src="/avatar-1.png">
                    </v-avatar>
                </v-col>
      </v-row>-->
      <div class="text-center mt-5">
        <v-avatar size="100" class="grey lighten-2">
          <img src="/avatar-1.png" />
        </v-avatar>
        <p class="white--text subheading mt-1">The Net Ninja</p>
      </div>

      <v-list>
        <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
          <v-list-item-action>
            <v-icon class="white--text">{{ link.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title class="white--text">{{link.text}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>

<script>
import CurrentUser from "./CurrentUser";
import NavigationLink from "./NavigationLink";

export default {
  name: "Navbar",
  components: { NavigationLink, CurrentUser },
  data: () => ({
    drawer: false,
    links: [
      { icon: "mdi-view-dashboard", text: "Dashboard", route: "/" },
      { icon: "mdi-folder", text: "My Projects", route: "/projects" },
      { icon: "mdi-account", text: "Team", route: "/team" }
    ],
    items: [{ title: "Item 1" }, { title: "Item 2" }],
    handlers: {
      on: {
        click: () => console.log("Clicked")
      }
    },
    user: {
      lastName: "Michalski"
    },
    url: '/profile'
  }),
  methods: {
    doNothing() {}
  }
};
</script>