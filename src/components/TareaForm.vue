<template>
  <form @submit.prevent="agregarTarea">
      <input type="text"
      placeholder="Ingrese Tarea"
      class="form-control my-2"
      v-model.trim="texto"
      >
  <button class="btn btn-primary w-100">Agregar</button>
  </form>
</template>

<script>
import {ref} from '@vue/reactivity'
import { inject } from '@vue/runtime-core'
export default {
  setup(){

    const texto = ref('')
    const tareas = inject('tareas')

    const agregarTarea = () => {
      if (texto.value === ''){
        return console.log('el campo esta vacio')
      }
      const tarea = {
          texto: texto.value,
          estado: false,
          id: Date.now()
      }
      tareas.value.push(tarea)
      texto.value = ''
    }
    return {agregarTarea, texto}
  }

}
</script>

<style>

</style>