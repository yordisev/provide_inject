<template>
<h1>App Tareas</h1>
<tarea-form/>
  {{tareas}}
</template>

<script>
import { ref } from '@vue/reactivity'
import TareaForm from './TareaForm.vue'
export default {
  components: { TareaForm },
setup(){
    const tareas = ref([])

    return {tareas}
}
}
</script>

<style>

</style>