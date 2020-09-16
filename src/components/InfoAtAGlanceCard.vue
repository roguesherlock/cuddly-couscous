<template>
  <div class="flex flex-wrap items-center justify-around">
    <div class="flex flex-col">
      <div
        class="rounded-full h-7 w-24 text-green-800 bg-green-300 font-semibold text-sm flex items-center justify-center"
      >
        {{ info.state }}
      </div>
      <div class="capitalize font-bold text-3xl">{{ info.name }}</div>
      <div v-for="action in info.actions" :key="action.name">
        <a
          class="inline-block py-2 px-4 bg-teal-500 rounded text-white font-semibold uppercase leading-snug hover:text-teal-900"
          :href="action.value"
          >{{ action.name }}</a
        >
      </div>
    </div>
    <div
      class="flex items-center justify-between"
      v-for="glanceInfo in info.atAGlanceInfo"
      :key="glanceInfo.value"
    >
      <GlanceInfoCard :info="glanceInfo" />
    </div>
  </div>
</template>
<script>
import GlanceInfoCard from "./GlanceInfoCard";

export default {
  name: "InfoAtAGlanceCard",
  props: {
    info: {
      name: String,
      state: String,
      atAGlanceInfo: [{ name: String, value: String }],
      actions: [{ name: String, value: String }],
    },
  },
  components: {
    GlanceInfoCard,
  },
};
</script>
