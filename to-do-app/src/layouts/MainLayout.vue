<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated>
      <q-toolbar>
        <!-- <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = !leftDrawerOpen"
        /> -->

        <q-toolbar-title class="absolute-center">
          Awesome Todo
        </q-toolbar-title>

      </q-toolbar>
    </q-header>

    <q-footer>
      <q-tabs>
        <q-route-tab
          v-for="nav in navs"
          :key="nav.name"
          :to="nav.link"
          :icon="nav.icon"
          :label="nav.title"
        />

      </q-tabs>
    </q-footer>

    <q-drawer
      v-model="leftDrawerOpen"
      :width="250"
      :breakpoint="767"
      show-if-above
      bordered
      content-class="bg-primary"
    >
      <q-list dark>
        <q-item-label header>
          Navigation
        </q-item-label>
        <EssentialLink
          v-for="link in navs"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink'

export default {
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  data () {
    return {
      leftDrawerOpen: false,
      navs: [
        {
          title: 'Todos',
          // caption: 'list of to-do items',
          icon: 'list',
          link: '/'
        },
        {
          title: 'Settings',
          // caption: 'list of to-do items',
          icon: 'settings',
          link: '/settings'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
@media screen and (min-width: 768px) {
  .q-footer {
    display: none;
  }
  .q-drawer {
    .q-router-link--exact-active {
      color: white !important;
    }
  }
}
</style>
