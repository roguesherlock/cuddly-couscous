<template>
  <div
    :style="{ marginLeft: '5.8rem' }"
    class="flex flex-col w-full h-full items-start justify-start mt-8"
  >
    <div class="font-bold text-2xl mt-8">History</div>
    <ul class="list-none max-w-md mt-6">
      <li
        :style="{ minHeight: '50px' }"
        class="ml-2 flex items-baseline box-content pb-10 p-0 m-0 relative border-l-2 border-teal-500"
      >
        <div
          :style="{ top: '0px', left: '-9px' }"
          class="h-4 w-4 rounded-full bg-teal-500 absolute"
        ></div>
        <div class="ml-4 pl-4 font-bold">now</div>
      </li>
      <li
        v-for="item in history"
        :key="item.name"
        :style="{ minHeight: '50px' }"
        class="ml-2 flex items-baseline box-content pb-10 p-0 m-0 relative border-l-2 border-teal-500"
      >
        <div
          :style="{ top: '2px', left: '-9px' }"
          class="h-4 w-4 rounded-full bg-teal-500 absolute"
        ></div>
        <div class="ml-8 ">
          <div class="text-gray-500 text-xs font-semibold leading-snug">
            {{ item.date }}
          </div>
          <div class="font-semibold text-lg">{{ item.name }}</div>
          <div v-if="item.data" class="text-sm">
            <template v-if="item.data.type === 'notes'">
              <div
                v-for="note in item.data.value"
                :key="note.name"
                class="flex flex-col text-gray-600 leading-5"
              >
                <div class="flex">
                  <p class="font-semibold ">{{ note.name }}</p>
                  <p class="ml-10 max-w-sm break-words">
                    {{ note.value }}
                  </p>
                </div>
              </div>
            </template>
            <template v-else-if="item.data.type === 'link'">
              <a
                class="text-teal-500 font-bold hover:text-teal-900"
                :href="item.data.value.value"
                >{{ item.data.value.name }}</a
              >
            </template>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HistoryCard",
  props: {
    history: Array,
    // history: [
    //   {
    //     date: String,
    //     name: String,
    //     data: Object,
    //   },
    // ],
  },
};
</script>
