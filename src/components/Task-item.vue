<template>
    <li class="flex justify-between mb-5  ">
    <button @click.self="$emit('complete')" class="focus:outline-none" :class="{'line-through': task.completed === true}">
      <input
        class="mx-1"
        type="checkbox"
        :checked="task.completed === true"
        @click.self="$emit('complete')"
      >{{ task.title }} </button> 
    <button class="hover:text-green-400 focus:outline-none" @click="$emit('remove')"><i class="far fa-trash-alt"></i></button>
  </li>
    
</template>

<script>
export default {
  name: "TaskItem",
  props: ["task"],

};
</script>