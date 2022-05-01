<script setup>
import { RouterView } from "vue-router";
</script>

<template>
  <header>
    <img
      alt="Structure for your own logo"
      class="logo"
      src="#Set the path"
      width="125"
      height="125"
    />
    <!-- If there is a Login view: -->
    <!-- <div v-if="!isUserLoged">
      <LoginView @allowLogin="handleLogin" @userToken="handleToken" />
    </div>
    <div v-else> -->
    <div>
      <!-- <HeaderComponent /> -->
      <!-- <NavbarComponent /> -->
      <router-view v-slot="{ Component }">
        <transition name="fade" mode="out-in">
          <!-- Here you can add the token, if any, to make it available in all views.
            ej: <KeepAlive exclude="#LoginComponent" :userToken="userToken"> -->
          <KeepAlive exclude="#LoginView">
            <component :is="Component" />
          </KeepAlive>
        </transition>
      </router-view>
      <!-- <FooterComponent /> -->
    </div>
  </header>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-display: auto;
  font-family: "Lucida Sans", "Lucida Sans Regular", "Lucida Grande",
    "Lucida Sans Unicode", Geneva, Verdana, sans-serif;
}
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.4s ease-in-out;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
