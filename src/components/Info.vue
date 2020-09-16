<template>
  <div class="flex flex-col flex-1 items-center justify-center mt-3">
    <div class="mt-6 max-w-6xl w-full">
      <InfoAtAGlanceCard
        :info="{
          name: infoObject.name,
          state: infoObject.state,
          actions: infoObject.actions,
          atAGlanceInfo: infoObject.atAGlanceInfo,
        }"
      />
    </div>
    <div class="mt-6 max-w-6xl w-full">
      <ul class="pl-8 flex ">
        <li class="-mb-px" @click="activateTab('activityActive')">
          <a
            :class="[
              tabStatus.activityActive ? tabActiveClasses : tabInactiveClasses,
            ]"
            class="py-2 px-4 flex items-center justify-around font-semibold"
            href="#"
            ><span
              ><svg
                class="w-6 h-6 mr-2"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M16 8v8m-4-5v5m-4-2v2m-2 4h12a2 2 0 002-2V6a2 2 0 00-2-2H6a2 2 0 00-2 2v12a2 2 0 002 2z"
                ></path></svg
            ></span>
            Activity</a
          >
        </li>
        <li @click="activateTab('detailsActive')">
          <a
            :class="[
              tabStatus.detailsActive ? tabActiveClasses : tabInactiveClasses,
            ]"
            class="py-2 px-4 flex items-center justify-around font-semibold"
            href="#"
            ><span
              ><svg
                class="w-6 h-6 mr-2"
                fill="none"
                stroke="currentColor"
                viewBox="0 0 24 24"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z"
                ></path></svg
            ></span>
            Details</a
          >
        </li>
      </ul>
    </div>
    <div class="w-full flex-1 bg-gray-300 border-t border-gray-400">
      <ActivityCard
        v-if="tabStatus.activityActive"
        :activity="infoObject.activity"
      />
      <DetailsCard
        v-if="tabStatus.detailsActive"
        :details="infoObject.details"
      />
    </div>
  </div>
</template>

<script>
import InfoAtAGlanceCard from "./InfoAtAGlanceCard";
import ActivityCard from "./ActivityCard";
import DetailsCard from "./DetailsCard";
export default {
  name: "Info",
  components: {
    InfoAtAGlanceCard,
    ActivityCard,
    DetailsCard,
  },
  data() {
    return {
      tabActiveClasses:
        "bg-gray-300 border-l border-r border-t rounded-t border-gray-400 text-teal-500",
      tabInactiveClasses: "text-gray-700",
      tabStatus: {
        activityActive: true,
        detailsActive: false,
      },
      infoObject: {
        name: "The Acredited Sales Executive (ASE) End-point app",
        state: "in progress",
        actions: [{ name: "Add Update", value: "#" }],
        atAGlanceInfo: [
          { name: "Due date", value: "12/02/20" },
          { name: "Amount (USD) ", value: "$250, 000.00" },
        ],
        details: [],
        activity: {
          now: {
            date: "Mon 12/02/19",
            name: "Next Step",
            reward: "earn 50,000 pts",
            data: {
              type: "notes",
              value: [
                {
                  name: "Add notes",
                  value:
                    "The Accredited Sales Executive (ASE) End-point Associate On-Demand Learning Program.",
                },
              ],
            },
            actions: [{ name: "Add your notes >", value: "#" }],
          },
          history: [
            {
              date: "Tue 5/02/2019",
              name: "Onsite meeting",
              data: {
                type: "notes",
                value: [
                  {
                    name: "Attendees",
                    value: "Art Vandelay, Jacki Chiles",
                  },
                  {
                    name: "Discussed",
                    value:
                      "Current network infrastructure design and Big5 focus areas for next FY. Proposed product test drive and/or SLR for next steps.",
                  },
                ],
              },
            },
            {
              date: "Wed 6/02/2019",
              name: "Prospects added from Penske Inc.",
              data: {
                type: "link",
                value: { name: "View prospects >", value: "#" },
              },
            },
            {
              date: "Thur 7/02/2019",
              name: "HPE Activity approved",
              data: null,
            },
          ],
        },
      },
    };
  },
  methods: {
    activateTab: function(tabName) {
      Object.keys(this.tabStatus).forEach((key) => {
        this.tabStatus[key] = false;
      });
      this.tabStatus[tabName] = !this.tabStatus[tabName];
    },
  },
};
</script>
