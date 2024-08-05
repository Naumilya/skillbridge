<script setup lang="ts">
import { ArrowRightIcon } from '@heroicons/vue/24/outline'

interface routeObj {
  nameRoute: string
  route: string
}
const routeList: routeObj[] = [
  {
    nameRoute: 'Home',
    route: '/'
  },
  {
    nameRoute: 'Courses',
    route: '/courses'
  },
  {
    nameRoute: 'About Us',
    route: '/about'
  },
  {
    nameRoute: 'Pricing',
    route: '/pricing'
  },
  {
    nameRoute: 'Contact',
    route: '/contact'
  }
]
</script>

<template>
  <header class="header">
    <div class="header__banner">
      <a href="/">
        <p>Free Courses 🌟 Sale Ends Soon, Get It Now</p>
        <ArrowRightIcon class="icon" />
      </a>
    </div>

    <nav class="navigation container">
      <div class="navigation__wrapper">
        <router-link to="/">
          <img src="@/assets/logo.svg" alt="logo" />
        </router-link>

        <ul class="menu">
          <li v-for="{ nameRoute, route } in routeList" :key="route">
            <router-link :to="route" class="menu__link"> {{ nameRoute }}</router-link>
          </li>
        </ul>
      </div>
      <div class="active-button">
        <router-link to="/sign-up">Sign Up</router-link>
        <router-link to="/login" class="active-button_accent">Login</router-link>
      </div>
    </nav>
  </header>
</template>

<style scoped>
a {
  text-decoration: none;
  color: var(--gray-15);
}

.header {
  padding: 20px 0;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.header__banner {
  padding: 14px 0;
  background-color: var(--orange-50);
  border-radius: 8px;
}

.header__banner a {
  display: flex;
  color: var(--white);
  justify-content: center;
  gap: 23px;
}

.header__banner p {
  /* padding: 14px 0; */
}

.navigation {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.navigation__wrapper {
  display: flex;
  gap: 50px;
  align-items: center;
}

.menu {
  display: flex;
  list-style: none;
  gap: 26px;
}

.menu__link {
  transition: all ease-in-out 0.2s;
}

.menu__link:hover {
  padding: 14px 24px;
  background-color: var(--white-95);
  border-radius: 8px;
}

.active-button {
  display: flex;
  align-items: center;
  gap: 30px;
}

.active-button_accent {
  background-color: var(--orange-50);
  padding: 14px 34px;
  color: var(--white);
  border-radius: 8px;
}
</style>
