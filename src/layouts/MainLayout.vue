<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        

        <q-toolbar-title>
          <q-img 
            src="../assets/logo.png"
            style="width:90px"             
          />
        </q-toolbar-title>

        <div>
          <q-btn 
            rounded
            label="Youtube"
            class="q-mr-xs"
            src="https://www.youtube.com/@headriser8241"
          ></q-btn>
          <q-btn 
            rounded
            label="Twitch"
            class="q-mr-xs"
            src="https://www.twitch.tv/kurisutina1"
          ></q-btn>
          <q-btn 
            rounded
            label="Telegram"
            src=""
          ></q-btn>
        </div>
        <div>
          <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="leftDrawerOpen = ! leftDrawerOpen"
        />
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
          Essential Links
        </q-item-label>

        <EssentialLink
          v-for="link in linksList"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>
    <router-view />
    <q-page-container class="bg-deep-black-1">
      <div class="row bg-primary">
        <div class="col">
          <div style="max-width:650px; text-align:center; margin-left:auto; margin-right:auto">
            <div class="text-h4 text-bold text-white q-mt-xl q-pt-xl q-bg-lg">Текст заглушка, ничего важного</div>
            <div class="text-white text-h6 q-pl-lg q-pr-lg q-pb-sm">Второй текст, ниже можно ввести потчу:</div>
            <q-input
              color="black"
              bg-color="white"
              filled
              placeholder="Your email"
              class="q-pl-lg q-pr-lg q-pb-lg"
            >
                <template v-slot:prepend>
                  <q-icon name="email"/>
                </template>
                <template v-slot:append>
                  <q-btn color="orange" label="smth"></q-btn>
                </template>
            </q-input>
          </div>
        </div>
        <div class="col gt-sm" >
          <q-img src="../assets/home.png"
          style="width:400px; margin-left:auto; margin-right: auto; display:block"
          ></q-img>
        </div>
      </div>
      <div class="row">
        <div class="text-h5 text-bold q-px-md q-pt-sm">Latest videos</div>
      </div>
      <div class="row">
        <div class="col-12 col-md">
          <div class="q-pa-md">
            <q-card class="my-card">
              <q-video src="https://www.youtube.com/embed/k3_tw44QsZQ?rel=0" />

              <q-card-section>
                <div class="text-h6">Our Changing Planet</div>
                <div class="text-subtitle2">by John Doe</div>
              </q-card-section>

              <q-card-section class="q-pt-none">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
                eiusmod tempor incididunt ut labore et dolore magna aliqua.
              </q-card-section>
            </q-card>
          </div>
        </div>
        <div class="col-12 col-md">
          <div class="q-pa-md">
            <q-card class="my-card">
              <q-video src="https://www.youtube.com/embed/k3_tw44QsZQ?rel=0" />

              <q-card-section>
                <div class="text-h6">Our Changing Planet</div>
                <div class="text-subtitle2">by John Doe</div>
              </q-card-section>

              <q-card-section class="q-pt-none">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
                eiusmod tempor incididunt ut labore et dolore magna aliqua.
              </q-card-section>
            </q-card>
          </div>
        </div>
        <div class="col-12 col-md">
          <div class="q-pa-md">
            <q-card class="my-card">
              <q-video src="https://www.youtube.com/embed/k3_tw44QsZQ?rel=0" />

              <q-card-section>
                <div class="text-h6">Our Changing Planet</div>
                <div class="text-subtitle2">by John Doe</div>
              </q-card-section>

              <q-card-section class="q-pt-none">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
                eiusmod tempor incididunt ut labore et dolore magna aliqua.
              </q-card-section>
            </q-card>
          </div>
        </div>
      </div>
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

defineOptions({
  name: 'MainLayout'
})

const linksList = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev'
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  }
]

const leftDrawerOpen = ref(false)

function toggleLeftDrawer () {
  leftDrawerOpen.value = !leftDrawerOpen.value
}
</script>
