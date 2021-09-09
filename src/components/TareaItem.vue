<template>
  <div class="alert alert-warning mt-3 d-flex justify-content-between align-items-center">
    <p class="m-0">{{tarea.texto}}</p>
    <div>
<i class="fas fa-undo-alt mx-2 text-success" role="button"
      @click="modificar(tarea.id)"
      ></i>

      <i class="fas fa-check-circle mx-2 text-success" role="button"
      @click="modificar(tarea.id)"
      ></i>
      <i class="fas fa-minus-circle text-danger"
      @click="eliminar(tarea.id)"
      ></i>
    </div>
  </div>
</template>

<script>
import { inject } from '@vue/runtime-core'
export default {
props:{
  tarea:{
    type:Object,
    required:true
  }
},
setup(){
    const tareas = inject('tareas')

    const eliminar = id => {
      tareas.value = tareas.value.filter(item => item.id !== id)
    }
  const modificar = id => {
    tareas.value = tareas.value.map(item => {
      if (item.id === id){
        item.estado = !item.estado
      }
      return item
    })
  }
  return {eliminar, modificar}
  }

}
</script>

<style>

</style>