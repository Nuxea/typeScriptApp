<script setup lang="ts">
import {ref} from "vue";
import Cards from "@/components/Cards.vue";

enum GENDER {
  MALE, FEMALE
}

interface INVITEE {
  id: number
  name: string
  gender: GENDER
}

const name = ref('')
const gender = ref(GENDER.MALE)

const invitees = ref<INVITEE[]>([])

const addInvitee = (): void => {
  if (name.value) {
    invitees.value.push({
      id: Math.floor(Math.random() * 10000000),
      name: name.value,
      gender: gender.value
    });
    name.value = ''
    gender.value = GENDER.MALE
  }


}
</script>

<template>
  <main>
    <div class="container">
      <h1>People invited to my party</h1>
      <div class="input-container">
        <input @keydown.enter="addInvitee" v-model="name" type="text" placeholder="Name...">
        <select @keydown.enter="addInvitee" v-model="gender">
          <option :value="GENDER.MALE">Male</option>
          <option :value="GENDER.FEMALE">Female</option>
        </select>
      </div>
      <div class="cards-container">
        <Cards v-for="invitee in invitees" :key="invitee.id" :invitee="invitee" />
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
