<template>
  <header>

    <div class="wrapper">
      <HelloWorld :users="users"/>
    </div>
  </header>

  <main>
    <!--<TheWelcome /> -->
  </main>
</template>


<script setup lang="ts">
import { ref } from 'vue';
import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
import type User from "@/types/User";

const users =ref<User[]>([ 
  {
    name:'Yassine',
    age:10
  },
  {
    name:'Kamal',
    age:23
  }
]);
</script>


<style scoped>
 
</style>
