<script setup>
import FancyButton from './components/icons/FancyButton.vue';
</script>

<template>
  <div class="content">
    <FancyButton>
      <template v-slot:icon="slotProps">
     {{ slotProps.hover ? '🚀' : '❌' }}
      </template>
      <template v-slot:default>
      <strong>E</strong>nviar
    </template>
    </FancyButton>

    <FancyButton>
      <template #icon="{ hover }">
       {{ hover ? '🚀' : '❌' }}
      </template>
      <template #default>
      <strong
      style="text-decoration: underline;">C</strong>ancelar
      </template>
    </FancyButton>
  </div>
</template>

<style scoped>
</style>
