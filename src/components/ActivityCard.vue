<template>
  <div class="flex-1 flex items-center">
    <div
      :style="{ height: '73vh', marginLeft: '5.8rem' }"
      class="flex items-start justify-center h-full w-1/2 border-r border-gray-400 pl-12 pt-12"
    >
      <NowCard :now="activity.now" />
    </div>
    <div
      :style="{ height: '73vh' }"
      class="flex items-center justify-center h-full w-1/2 bg-white"
    >
      <HistoryCard :history="activity.history" />
    </div>
  </div>
</template>

<script>
import NowCard from "./NowCard";
import HistoryCard from "./HistoryCard";

export default {
  name: "ActivityCard",
  components: { NowCard, HistoryCard },
  props: {
    activity: Object,
  },
};
</script>
