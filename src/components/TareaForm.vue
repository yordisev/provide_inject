<template>
  <form @submit.prevent="agregarTarea">
      <input type="text"
      placeholder="Ingrese Tarea"
      class="form-control my-2"
      v-model="texto"
      >
  <button class="btn btn-primary w-100">Agregar</button>
  </form>
</template>

<script>
import {inject, ref} from 'vue'
export default {
  setup(){

    const texto = ref('')
    const tareas = inject('tareas')

    const agregarTarea = () => {

    }
    return {agregarTarea, texto}
  }

}
</script>

<style>

</style>