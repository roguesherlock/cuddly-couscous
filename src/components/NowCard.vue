<template>
  <div
    class="flex flex-col justify-around max-w-md bg-gray-100 border border-gray-500 rounded"
  >
    <div class="w-full text-xl p-4 font-bold text-left">{{ now.name }}</div>
    <div
      class="w-full flex-1 shadow px-4 py-2 flex text-white font-bold text-md items-center justify-between bg-blue-900"
    >
      <div>Due: {{ now.date }}</div>
      <div>{{ now.reward }}</div>
    </div>
    <div
      v-for="item in now.data.value"
      :key="item.name"
      class=" w-full px-4 py-2 mt-3 flex flex-col"
    >
      <p class="font-bold">{{ item.name }}</p>
      <p class="text-gray-700">{{ item.value }}</p>
    </div>
    <div
      v-for="action in now.actions"
      :key="action.name"
      class="w-full px-4 py-2 mt-3 flex"
    >
      <a
        class="text-teal-500 font-bold hover:text-teal-900"
        :href="action.value"
        >{{ action.name }}</a
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "NowCard",
  props: {
    now: Object,
  },
};
</script>
