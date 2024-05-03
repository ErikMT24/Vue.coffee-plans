<script setup>
import { ref } from 'vue';
const hover = ref(false);
</script>

<template>
<header>
    <div>
    </div>
  </header>

  <div class="content">
    <button 
    @mouseenter="hover = true"
    @mouseleave="hover = false">
      <slot name="icon" :hover="hover"> ⚠ </slot>
      <slot>No Message</slot>
    </button>
  
  </div>
</template>

<style scoped>
.content{
  text-align: center;
}

button{
  width: 15rem;
  margin: 30px auto;
  font-size: 2rem;
}
</style>
