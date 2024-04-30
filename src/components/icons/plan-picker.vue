<template>
    <div ref="plansWrapper" 
    class="plans">
          <plan-picker-item
           @select="printSelected"
           :selectedPlan="selectedPlan"
           v-for="plan in plans"
          :name="plan"
          v-bind:key="plan"/>
          <p style="font-size: 30px;">Counter: {{ counter }}</p>
        </div>
    </template>
    
    <script setup>

    import {onMounted, onUnmounted, ref, } from 'vue';
     import planPickerItem from './plan-picker-item.vue';
     const plans = ref([
        "El soltero",
        "El adicto",
        "El viajero"]);
        const plansWrapper = ref(null);
    
        const selectedPlan =ref(null);
    
        const printSelected = (playload) => {
        selectedPlan.value = playload;
        }
        //Creanod una referencia reactiva.
        //para un contador    
        const counter = ref(0);
        //Creando un metodo para incrementar el contaador 
         const processId = setInterval(() =>{
            console.log('incrementando contador');
         counter.value++;
        }, 1000);

        //Registrando el CB (Call back) onMounted
          onMounted ( () => {
        //Obteniendo la referencia del elemento plans
        console.log('Componente Plan Picker montado');
          });

          //Reistrando el CB de OnUnmounted
          onUnmounted (() =>{
           console.log('Componente Plan Picker desmontado')
           clearInterval(processId);
          });
    </script>