<template>
    <li class="flex justify-between py-2 ">
    <button @click.self="$emit('complete')" class="focus:outline-none round max-w-xs" :class="{'line-through': task.completed === true}">
  
    <input
        class="mx-1"
        id="checkbox"
        type="checkbox"
        :checked="task.completed === true"
      >    <label  for="checkbox"></label>
      
      {{ task.title }} </button> 

    <button class="hover:text-green-400 focus:outline-none" @click="$emit('remove')"><i class="far fa-trash-alt"></i></button>
  </li>
    
</template>

<script>
export default {
  name: "TaskItem",
  props: ["task"],

};
</script>