<template>
  <q-layout view="lHh Lpr lFf">
    <q-header>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

      </q-toolbar>
      <div class="q-px-lg q-pt-xl q-mb-md">
        <div class="text-h3">Prime-Quasar</div>
        <div class="text-subtitle1">{{ todaysDate}}</div>
      </div>
      <q-img
         src="double-exposure.jpg"
        class="header-image absolute-top"/>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered

      :width="250"
        :breakpoint="600"
    >

      <q-list>

          header
        >

<EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
/>
      </q-list>
        <q-scroll-area style="height: calc(100% - 164px); margin-top: 164px; border-right: 1px solid #ddd">
          <q-list padding>
            <q-item
            to="/"
            exact
            clickable
            v-ripple>
              <q-item-section avatar>
                <q-icon name="list" />
              </q-item-section>

              <q-item-section>
                Prime-Quasar
              </q-item-section>
            </q-item>

            <q-item
            to="/help"
              clickable
              v-ripple>
              <q-item-section avatar>
                <q-icon name="help" />
              </q-item-section>

              <q-item-section>
                Help
              </q-item-section>
            </q-item>

            <q-item clickable v-ripple>
              <q-item-section avatar>

              </q-item-section>

              <q-item-section>

              </q-item-section>
            </q-item>

            <q-item clickable v-ripple>
              <q-item-section avatar>

              </q-item-section>

              <q-item-section>

              </q-item-section>
            </q-item>
          </q-list>
        </q-scroll-area>

        <q-img class="absolute-top" src="girls-369788_1280.jpg" style="height: 164px">
          <div class="absolute-bottom bg-transparent">
            <q-avatar size="56px" class="q-mb-sm">
              <img src="music-1020087_1280.jpg">
            </q-avatar>
            <div class="text-weight-bold">Leo do Rosario</div>
            <div>https://github.com/leodorosario</div>
          </div>
        </q-img>
    </q-drawer>

    <q-page-container>
      <Keep-alive>
        <router-view />
      </Keep-alive>
    </q-page-container>
  </q-layout>
</template>

<script>

import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [

]

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }

    }
  },
  Computed: {
    todaysDate () {

    }

  }
})

</script>

<style lang="scss">
  .header-image {
    height: 100%;
    z-index: -1;
    opacity: 1;
    filter: bluescale(100%);

}

</style>
