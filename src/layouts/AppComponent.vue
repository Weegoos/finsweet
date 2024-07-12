<template>
  <div>
    <q-layout view="hHr LpR lFf" container style="height: 100vh">
      <q-header reveal elevated bordered>
        <q-toolbar class="text-white" style="background-color: #232536">
          <div v-show="isMobile">
            <q-btn flat icon="menu" @click="drawer = !drawer" />
          </div>
          <q-toolbar-title class="q-ml-md"> {Finsweet </q-toolbar-title>
          <div class="q-gutter-sm" v-show="isDesktop">
            <q-btn flat no-caps label="Home" />
            <q-btn flat no-caps label="Blog" />
            <q-btn flat no-caps label="About us" />
            <q-btn flat no-caps label="Contact us" />
            <q-btn
              flat
              no-caps
              label="Subscribe"
              class="bg-white text-black q-pa-sm"
              style="width: 180px"
            />
          </div>
        </q-toolbar>
      </q-header>
      <q-drawer
        v-if="isMobile"
        mini-to-overlay
        v-model="drawer"
        show-if-above
        bordered
        :width="[$q.screen.width < 850 ? '300' : '150']"
        :breakpoint="500"
        content-class="bg-grey-3"
      >
        <q-list>
          <q-item
            clickable
            v-ripple
            v-for="btn in button"
            :key="btn.name"
            @click="navigate(btn.link)"
          >
            <q-item-section class="q-pl-md">{{ btn.name }}</q-item-section>
          </q-item>
        </q-list>
      </q-drawer>
      <q-page-container>
        <q-page>
          <router-view />
        </q-page>
      </q-page-container>
    </q-layout>
  </div>
</template>

<script setup>
import { onMounted, onUnmounted, ref } from "vue";
import { useRouter } from "vue-router";

const isDesktop = ref(false);
const isMobile = ref(false);
const width = ref(window.innerWidth);
const transitionDevice = 750;
const drawer = ref(false);

const updateWidth = () => {
  width.value = window.innerWidth;
  isDesktop.value = width.value >= transitionDevice;
  isMobile.value = width.value < transitionDevice;
};

updateWidth();

onMounted(() => {
  window.addEventListener("resize", updateWidth);
});

onUnmounted(() => {
  window.removeEventListener("resize", updateWidth);
});

const button = [
  {
    name: "Home",
    link: "/",
  },
  {
    name: "Blog",
    link: "/blog",
  },
  {
    name: "About us",
    link: "/about",
  },
  {
    name: "Contact us",
    link: "/contact",
  },
  {
    name: "Subscribe",
    link: "/subscribe",
  },
];

const router = useRouter();
const navigate = (route) => {
  router.push(route);
};
</script>

<style></style>
