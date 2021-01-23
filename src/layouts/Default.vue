<template>
  <v-app>
    <v-navigation-drawer width="240px" permanent color="indigo lighten-4" fixed>
      <v-list-item>
        <v-list-item-avatar>
          <!-- <v-img src="https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&a"></v-img> -->
          <v-avatar color="primary" size="56">
            <span class="white--text" style="user-select: none">MN</span>
          </v-avatar>
        </v-list-item-avatar>
        <v-list-item-content>
          <v-list-item-title class="title"> Mahdi Niknejad</v-list-item-title>
          <v-list-item-subtitle> Software Developer </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          link
          :to="`#${item.title.toLowerCase()}`"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <!-- <header class="header">
      <strong>
        <g-link to="/">{{ $static.metadata.siteName }}</g-link>
      </strong>
      <nav class="nav">
        <g-link class="nav__link" to="/">Home</g-link>
        <g-link class="nav__link" to="/about/">About</g-link>
      </nav>
    </header> -->
    <v-main>
      <slot />
    </v-main>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { title: "About", icon: "mdi-account-box" },
        { title: "Projects", icon: "mdi-apps" },
        { title: "Education", icon: "mdi-school" },
        { title: "Contact", icon: "mdi-message-text" },
      ],
      mode: "dark",
    };
  },
  metaInfo: {
    title: "Mahdi Niknejad",
  },
};
</script>



<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>


<style>
html {
  scroll-behavior: smooth;
}
.v-application--wrap {
  flex-direction: row;
}
.v-main {
  flex: 1 0;
  margin-left: 240px;
}
</style>