<script setup lang="ts">
import {ref} from "vue";

enum GENDER {
  MALE, FEMALE
}

const name = ref('')
const gender = ref(GENDER.MALE)
</script>

<template>
  <main>
    <div class="container">
      <h1>People invited to my party</h1>
      <div class="input-container">
        <input v-model="name" type="text" placeholder="Name...">
        <select v-model="gender">
          <option :value="GENDER.MALE">Male</option>
          <option :value="GENDER.FEMALE">Female</option>
        </select>
      </div>
    </div>
  </main>
</template>

<style scoped>
main {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

input, select {
  width: 100%;
  padding: 10px;
  margin-bottom: 5px;
  border: none;
  border-radius: 5px;
}
</style>
