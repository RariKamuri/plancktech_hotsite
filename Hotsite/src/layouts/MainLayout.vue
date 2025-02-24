<template>
  <q-layout view="lHh Lpr lFf" class="main-layout">
    <div class="background-image"></div>
    <q-header elevated class="transparent-header no-shadow pt-5">
      <q-toolbar class="bg-transparent">
        <q-toolbar-title class="flex items-center no-padding"
        >
        <svg 
            xmlns="http://www.w3.org/2000/svg" 
            viewBox="0 0 3599.19 631.49"
            class="logo-svg q-mr-sm"
          >
            <!-- New SVG paths -->
            <path class="cls-2" d="M920.72,204.28h108.72c22.56,0,44,1.48,60.64,18.12,16.64,16.64,21.08,33.65,21.08,52.88v2.96c0,18.86-4.44,36.24-21.08,52.88-16.64,16.64-38.09,17.75-60.64,17.75h-76.17v116.48h-32.54V204.28ZM953.26,322.61h87.27c14.05,0,25.15-2.96,33.28-12.2,4.44-5.18,4.44-8.14,4.44-19.23v-29.58c0-11.09,0-14.05-4.44-19.23-8.13-9.24-19.23-12.2-33.28-12.2h-87.27v92.45Z"/>
            <!-- Include all other paths from the new SVG -->
            <path class="cls-3" d="M312.34,307.12l-75.74-203.48c-6.05-16.24,11.71-31.05,26.6-22.18l137.57,81.96"/>
            <path class="cls-3" d="M667.44,307.12l75.74-203.48c6.05-16.24-11.71-31.05-26.6-22.18l-133.53,79.55"/>
            <path class="cls-2" d="M717.35,361.34l-99.74-206.98c-2.91-6.72-9.53-11.07-16.85-11.07h-222.32c-7.01,0-13.4,3.99-16.49,10.28l-101.45,207.05c-3.82,7.8-1.65,17.21,5.2,22.56l212.38,165.63c6.78,5.29,16.33,5.16,22.97-.31l211.14-165.7c6.31-5.2,8.42-13.95,5.17-21.46Z"/>
            <path class="cls-2" d="M1154.42,204.28h32.54v234.44h138.67v26.62h-171.21V204.28Z"/>
            <path class="cls-2" d="M1525.68,465.34l-17.01-64.71h-122.03l-17.38,64.71h-32.54l70.63-261.07h81.35l70.63,261.07h-33.65ZM1501.27,374.38l-38.09-144.21h-31.43l-38.09,144.21h107.61Z"/>
            <path class="cls-2" d="M1597.41,204.28h38.09l119.44,210.78v-210.78h32.91v261.07h-38.09l-119.81-210.04v210.04h-32.54V204.28Z"/>
            <path class="cls-2" d="M1842.21,369.94v-69.52c0-57.32,47.33-103.17,105.76-103.17,38.09,0,73.96,19.6,92.45,52.51l-15.53,14.05c-52.14-32.91-58.43-40.31-76.92-40.31-26.99,0-51.4,13.31-66.19,36.24-5.92,8.88-5.92,17.75-5.92,28.47v92.82c0,11.09,0,19.97,5.92,28.84,14.79,22.93,39.2,36.24,66.19,36.24,18.49,0,24.78-7.4,76.92-40.68l15.53,14.05c-18.49,32.91-54.36,52.88-92.45,52.88-58.42,0-105.76-46.96-105.76-102.43Z"/>
            <path class="cls-2" d="M2084.05,204.28h32.54v115h35.13l94.66-115h38.83l-106.5,127.57,106.5,133.49h-39.94l-94.29-120.18h-34.39v120.18h-32.54V204.28Z"/>
            <path class="cls-2" d="M2538.14,230.9v234.44h-32.17v-234.44h-87.64v-26.62h206.71v26.62h-86.9Z"/>
            <path class="cls-2" d="M2660.17,465.34V204.28h176.75v26.62h-144.21v88.01h122.4v26.62h-122.4v93.55h144.21v26.25h-176.75Z"/>
            <path class="cls-2" d="M2872.42,369.94v-69.52c0-57.32,47.33-103.17,105.76-103.17,38.09,0,73.96,19.6,92.45,52.51l-15.53,14.05c-52.14-32.91-58.43-40.31-76.92-40.31-26.99,0-51.4,13.31-66.19,36.24-5.92,8.88-5.92,17.75-5.92,28.47v92.82c0,11.09,0,19.97,5.92,28.84,14.79,22.93,39.2,36.24,66.19,36.24,18.49,0,24.78-7.4,76.92-40.68l15.53,14.05c-18.49,32.91-54.36,52.88-92.45,52.88-58.42,0-105.76-46.96-105.76-102.43Z"/>
            <path class="cls-2" d="M3114.26,204.28h32.54v114.63h124.99v-114.63h32.91v261.07h-32.91v-119.81h-124.99v119.81h-32.54V204.28Z"/>
          </svg>
        </q-toolbar-title>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
          style="margin-top: 3px;"
        />
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      show-if-above
      bordered
    >
      <q-list>
        <EssentialLink
          v-for="link in linksList"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container class="px-5" style="padding-top: 0px !important;">
      <router-view />
    </q-page-container>
    <q-footer elevated class="bg-transparent no-shadow">
      <q-toolbar class="justify-between bg-transparent">
        <!-- Static SVG -->
        <svg 
          xmlns="http://www.w3.org/2000/svg" 
          viewBox="0 0 139.65 179.33"
          class="footer-logo"
          aria-hidden="true"
        >
          <path class="cls-1" d="M67.15,179.33c-7.87,0-15.05-4.11-19.05-11.03L2.93,90.1c-6-10.39-2.5-23.85,7.81-29.99h0S106.34,3.16,106.34,3.16c8.13-4.85,18.08-4.06,25.35,2,7.27,6.07,9.84,15.71,6.54,24.58l-50.33,135.22c-3.01,8.09-10.22,13.57-18.82,14.29-.64.06-1.28.08-1.91.08ZM18.04,72.34c-3.65,2.18-4.89,6.95-2.77,10.63l45.17,78.2c1.56,2.69,4.4,4.06,7.43,3.88,3.1-.26,5.59-2.16,6.67-5.06L124.87,24.78c1.78-4.78-1.32-7.85-2.31-8.67-.99-.82-4.56-3.32-8.94-.7L18.04,72.34Z"/>
        </svg>

        <!-- Copyright Text -->
        <div class="text-caption text-right q-pr-md">
          © {{ new Date().getFullYear() }} Planck Tech. All rights reserved.
        </div>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'Whatsapp',
    caption: 'whatsapp',
    icon: 'chat',
    link: 'https://wa.me/555192461105'
  },
  {
    title: 'LinkedIn',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://www.linkedin.com/in/natanungethuem/'
  },
]

const leftDrawerOpen = ref(false)

function toggleLeftDrawer () {
  leftDrawerOpen.value = !leftDrawerOpen.value
}
</script>
<style scoped>
.px-5{
  padding-left: 15px;
  padding-right: 15px;
}
.pt-5{
  padding-top: 15px;
}
:deep(.q-layout__shadow) {
  display: none !important;
}
/* Main layout styles */
.main-layout {
  position: relative;
  min-height: 100vh;
}

.background-image {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url('/src/assets/images/PLANCKBG.png');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  z-index: 0;
}

.transparent-header, .transparent-footer {
  background-color: transparent !important;
  box-shadow: none !important;
  position: relative;
  z-index: 1;
}

.q-page-container {
  position: relative;
  z-index: 1;
  background: transparent !important;
}

.q-drawer {
  background-color: rgba(255, 255, 255, 0.9) !important;
  backdrop-filter: blur(5px);
  box-shadow: none !important;
}

/* Make page content transparent */
.q-page-container {
  background-color: transparent !important;
}

/* Logo adjustments */
.logo-svg {
  height: 45px;
  width: auto;
  vertical-align: middle;
  transform: scale(1.2);
  transform-origin: left center;
}

.cls-1 {
  /*font-family: 'Kade-Regular', 'Kade', sans-serif;*/
  fill: #fff;
}

.cls-2 {
  fill: #fff;
}

.cls-3 {
  fill: #ddd;
}

/* .cls-1, .cls-2, .cls-3 {
  stroke-width: 0px;
} */

.q-toolbar-title {
  align-items: center !important;
  padding-bottom: 0 !important;
}

.q-toolbar-title span {
  line-height: 1;
  position: relative;
  top: 1px; /* Optical alignment */
}
</style>

<!-- Add global styles to your quasar.config.js or App.vue -->
<style>
/* Global transparent elements */
.q-menu, .q-card {
  background-color: rgba(255, 255, 255, 0.95) !important;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(0, 0, 0, 0.1) !important;
}

/* List items transparency */
.q-item {
  background-color: transparent !important;
}

.footer-logo {
  height: 35px;
  width: auto;
}

.cls-1 {
  fill: #689A2F; /* Brand green color */
}

.q-footer{
  margin-bottom: 15px;
}

.q-footer .q-toolbar {
  min-height: 55px;
  padding: 0 30px;
}

</style>