<script setup lang="ts">
let name = "Amandine";
let age = 30;
let sex = true;
let occupation: string;

occupation = 'software developer'

age = 26
// sex = 'female'

const arrayOfNumbers: (string | number)[] = []

arrayOfNumbers.push(name)
arrayOfNumbers.push(age)

// const employee: {
//   name: string,
//   age: number,
//   sex: boolean,
//   occupation?: string
// } = {
//   name: 'Amandine',
//   age: 30,
//   sex: true
// }

interface Employee {
  name: string,
  age: number,
  sex: GENDER,
  occupation?: string
}

enum GENDER {
  FEMALE, MALE, NONBINARY
}
const employee: Employee = {
  name: "Amandine",
  age: 30,
  sex: GENDER.FEMALE
}

employee.occupation = 'Software Developer'
employee.sex = GENDER.MALE
employee.sex = GENDER.NONBINARY
</script>

<template>
  <main></main>
</template>

<style scoped>

</style>
