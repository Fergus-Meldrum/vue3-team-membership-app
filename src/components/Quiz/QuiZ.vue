<script setup>
import QuizHeader from '@/components/Quiz/QuizHeader.vue'
import QuizQuestion from '@/components/Quiz/QuizQuestion.vue'
import QuizFooter from '@/components/Quiz/QuizFooter.vue'
import { provide, ref } from 'vue'

let name = ref('John Doe')
</script>

<template>
  <h1>{{ name }}</h1>
  <QuizHeader />
  <QuizQuestion />
  <QuizFooter />
</template>
