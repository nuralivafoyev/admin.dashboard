<template>
    <aside :class="{ 'collapsed': isCollapsed }">
      <div class="asside-top">
        <a class="logo" href="/">
          <img src="../images/icons/logo.svg" alt="logo">
          <h4 v-if="!isCollapsed">Dashboard</h4>
          <span v-if="!isCollapsed">v.01</span>
        </a>
  
        <!-- Sidebarni kichraytirish uchun tugma -->
        <button @click="toggleSidebar" class="toggle-btn">
          <span v-if="isCollapsed">☰</span>
          <span v-else>×</span>
        </button>
  
        <!-- Navigatsiya ro'yxati -->
        <ul v-if="navLinks.length" class="list">
          <li class="list-item" v-for="el in navLinks" :key="el.path">
            <router-link class="list-item-link" :to="el.path">
              <div class="list-item-icon" v-html="el.icon"></div>
              <span v-if="!isCollapsed">{{ el.name }}</span> <!-- Yozuv faqat katta holatda ko'rinadi -->
            </router-link>
          </li>
        </ul>
      </div>
  
      <div class="asside-bottom">
        <!-- Proga kirish imkoniyati faqat katta sidebarda -->
        <div v-if="!isCollapsed" class="pro-access">
          <h4>Upgrade to PRO to get access all Features!</h4>
          <button>Get Pro Now!</button>
        </div>
        <!-- Logout bo'limi -->
        <div class="logout">
          <img src="../images/images/putin.jpg" alt="user">
          <h5 v-if="!isCollapsed">Putin<span>Project Manager</span></h5>
        </div>
      </div>
    </aside>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import { navLinks } from '@/constants';  // Nav linklarni import qilish
  
  // Sidebarning holatini boshqarish
  const isCollapsed = ref(false);
  
  // Sidebarni kichraytirish va kengaytirish uchun metod
  const toggleSidebar = () => {
    isCollapsed.value = !isCollapsed.value;
  };
  </script>


<style scoped lang="scss" src="./_style.scss"></style>