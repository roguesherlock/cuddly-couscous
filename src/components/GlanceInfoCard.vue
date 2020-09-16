<template>
  <div
    :style="{ minWidth: '10rem' }"
    class="flex flex-col rounded border border-gray-300"
  >
    <div class="bg-teal-200 py-2 px-4 font-bold text-center rounded-t">
      {{ info.name }}
    </div>
    <div
      :style="{ minHeight: '5rem' }"
      class="flex items-center justify-center h-16 rounded-b text-gray-700 text-lg"
    >
      {{ info.value }}
    </div>
  </div>
</template>
<script>
export default {
  name: "GlanceInfoCard",
  props: {
    info: { name: String, value: String },
  },
};
</script>
