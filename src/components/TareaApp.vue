<template>
<h1>App Tareas</h1>
<tarea-form/>
  {{tareas}}
</template>

<script>
import {ref } from '@vue/reactivity'
import TareaForm from './TareaForm.vue'
import { provide } from '@vue/runtime-core'
export default {
  components: { TareaForm },
setup(){
    const tareas = ref([])

   provide('tareas', tareas)

    return {tareas}
}
}
</script>

<style>

</style>