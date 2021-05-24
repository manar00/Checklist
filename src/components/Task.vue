<template>
  <div class=" py-5 max-w-screen-sm ">
    <div class=" bg-white rounded-2xl p-8 shadow-sm">
      <!-- title -->
      <div class="text-center mb-8">
        <h1 class="text-xl">Checklist</h1>
              <!-- pending task -->
      <div class="py-5">
        <span>1/7 </span>
      </div>
      </div>
      <!-- form -->
      <div class="relative mb-8">
        <input class="p-2 rounded w-full h-10 text-current bg-gray-50 text-gray-500	border border-solid border-opacity-0 focus:border-blue-500 focus:outline-none " type="text" placeholder="New Task" />
        <button class="absolute top-2 right-5 focus:outline-none text-xl text-green-600"><i class="fas fa-plus"></i></button>
      </div>
      <!-- task lists -->
      <div class="py-2">
        <ul>
          <li class="flex justify-between mb-5 ">
            <button>Learn Vue JS</button>
            <button class="hover:text-green-300 focus:outline-none"><i class="far fa-trash-alt"></i></button>
          </li>
     
        </ul>
      </div>
      <!-- buttons -->
      <div class="hover:bg-black">
        <button class="w-full p-2 rounded-xl text-white	my-2 focus:outline-none" style="background: #4ec5c1;">Clear completed</button>
        <button class=" w-full p-2 rounded-xl text-white my-2 focus:outline-none" style="background: #4ec5c1;">Clear all</button>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: "Task",
};
</script>