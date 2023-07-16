
<template>
  <div v-for="(user,key) in props.users" :key="key">
    <span > {{ user.name }} </span>
    <span > and age is  {{  user.age }} </span>
  </div>
  <button @click="display('name')">éditer Subtitle</button>
  <button @click="display('age')">display</button>

  <br>
  <div v-for="item in displayProperty">
    <span>{{item}}</span>
  </div>
</template>

<script setup lang="ts">
import type User from "@/types/User";
import type UserProperties from '@/types/UserType';
import { ref } from "vue";
  

const displayProperty = ref<any>([]);

  const props = defineProps<{
    users: User[],
  }>();

  const display = (property: UserProperties) => {
    displayProperty.value = []
    props.users.forEach((item:User)=>{
      console.log(item[property]);
      displayProperty.value.push(item[property]);
    });
    console.log("property", property);
  }














const title = ref<string>("hello world");
  const subTitle = ref<string | number>(90);

  const state = ref({
    title:'Hello World' as string,
    subTitle :90 as string | number,
  })

  const editTitle = (editedTitle:string) => {
    title.value = editedTitle;
  }

  const editSubTitle = (editedSubttitle:any)=>{
    subTitle.value = editedSubttitle
  }
</script>


<style scoped>

</style>
