<script setup>
import TeamMember from '@/components/TeamApp/TeamMember.vue'

import { useTeamStore } from '@/stores/TeamStore.js'

let team = useTeamStore()
</script>

<template>
  <table class="table-fixed border-spacing-2 border-separate">
    <thead>
      <th class="text-left px-6 py-2">Name</th>
      <th class="text-left px-6 py-2">Email</th>
      <th class="text-left px-6 py-2">Status</th>
    </thead>
    <tbody>
      <TeamMember
        v-for="member in team.members"
        :id="member.id"
        :name="member.name"
        :email="member.email"
      />
    </tbody>
  </table>
  <p class="text-right text-gray-600 italic" v-show="team.maxSpotsReached">
    There are no remaining team spots. Upgrade to add more.
  </p>
</template>

<style scoped></style>
