<template>
  <v-app>
    <!-- <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    > -->
    <!-- <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list> -->
    <!-- </v-navigation-drawer> -->
    <v-app-bar :clipped-left="clipped" fixed app>
      <!-- <v-app-bar-nav-icon @click.stop="drawer = !drawer" /> -->
      <!-- <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn> -->
      <!-- <v-btn icon @click.stop="clipped = !clipped">
        <v-icon>mdi-application</v-icon>
      </v-btn>
      <v-btn icon @click.stop="fixed = !fixed">
        <v-icon>mdi-minus</v-icon>
      </v-btn> -->
      <!-- <v-toolbar-title v-text="title" /> -->
      <v-img src="img/icon.png" max-height="40" max-width="40" contain></v-img>
      <v-img src="img/wings.png" max-height="40" max-width="90" contain></v-img>
      <v-spacer />
      <v-btn icon @click.stop="rightDrawer = !rightDrawer">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <!-- <v-container fluid> -->
      <nuxt />
      <!-- </v-container> -->
    </v-main>
    <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-subtitle>
            個人向けコンテンツ翻訳サービス
          </v-list-item-subtitle>
          <v-list-item-title class="mt-4 wings"> Wings </v-list-item-title>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>
      <v-list dense>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          @click.prevent="onClick(item.path)"
        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <!-- <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light> mdi-repeat </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list> -->
    </v-navigation-drawer>
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }} {{ title }}</span>
    </v-footer>
  </v-app>
</template>
<style scoped>
.wings {
  font-family: 'Kalam', serif;
  font-size: 40px;
}
</style>
<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-home',
          title: 'Top',
          path: '#Hero',
        },
        {
          icon: 'mdi-lightbulb-on-outline',
          title: 'Vision',
          path: '#Vision',
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Service',
          path: '#Service',
        },
        {
          icon: 'mdi-message-text-outline',
          title: 'Contact',
          path: 'https://forms.gle/7pQ6PnjvHtTj3Bb6A',
        },
        {
          icon: 'mdi-post-outline',
          title: '開発者ブログ',
          path: 'https://medium.com/@norito.sasaki',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'WINGS',
    }
  },
  methods: {
    isInternalLink(path) {
      return !/^https?:\/\//.test(path)
    },
    onClick(path) {
      if (this.isInternalLink(path)) {
        this.$router.push(path)
      } else {
        location.href = path
      }
    },
  },
}
</script>
