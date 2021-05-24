<template>
  <div class=" py-5 max-w-screen-sm ">
    <div class=" bg-white rounded-2xl p-8 shadow-sm">
      <!-- title -->
      <div class="text-center">
        <h1 class="text-xl">Checklist</h1>
              <!-- completed task -->
      <div class="py-2">
        <span>{{ incomplete }}/{{tasks.length}} </span>
      </div>
      </div>
      <!-- form -->
      <div class="relative mb-8">

        <input v-model="addNewTask"
          @keyup.enter="addTask" class="p-2 rounded w-full h-10 text-current bg-gray-50 text-gray-500	border border-solid border-opacity-0 focus:border-blue-500 focus:outline-none " type="text" placeholder="New Task" />
        <button @click="addTask" class="absolute top-2 right-3 focus:outline-none text-xl text-green-400"><i class="fas fa-plus"></i></button>
      </div>
      <!-- task lists -->
      <div class="py-2">
        <ul>
          <task-item
            v-bind:task="task"
            v-for="(task, index) in tasks"
            :key="task.id"
            @remove="removeTask(index)"
            @complete="completeTask(task)"
          ></task-item>
     
        </ul>
      </div>
      <!-- buttons -->
      <div>
        <button class="w-full p-2 rounded-xl text-white	my-2 focus:outline-none hover:bg-black bg-green-400"   @click=" tasks = tasks.filter(completed)">Clear completed</button>
        <button class=" w-full p-2 rounded-xl text-white my-2 focus:outline-none hover:bg-black bg-green-400"  @click="tasks =[]">Clear all</button>
      </div>

    </div>
  </div>
</template>

<script>
import TaskItem from "./Task-item";

export default {
  name: "Task",
   props: {
    tasks: {
      type: Array
    }
  },
  
  components: {
    TaskItem,
  },
    data() {
    return {
      addNewTask: "",
    };
  },
computed: {
    incomplete() {
      return this.tasks.filter(this.completed).length;
    },
  },
  methods:{
    addTask() {
      if (this.addNewTask) {
        this.tasks.push({
          title: this.addNewTask,
          completed: false,
        });
        this.addNewTask = "";
      }
    },
    completed(task) {
      return this.isCompleted(task);
    },
    isCompleted(task) {
      return task.completed;
    },

    completeTask(task) {
      task.completed = !task.completed;
    },
    removeTask(index) {
      this.tasks.splice(index, 1);
    },
  },
  }

</script>