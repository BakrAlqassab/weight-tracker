

<script>
 /* eslint-disable */
import { ref, shallowRef, computed, watch, nextTick } from "vue";
import chart from "chart.js/auto";

const weights = ref([]);
const weightChart = shallowRef(null);
const weightChartEl = ref(null);
const weightInput = ref(60.0);


const currentWeight = computed(() => {
  return weights.value.sort((a, b) => b.date - a.date)[0] || { weight: 0 };
});

const addWeight = () => {
  weights.value.push({
    weight: weightInput,
    date: new Date.getTime(),
  });
};

export default {
  name: "weight-tracker",

  components: {},
};
</script>

<template>
  <main>
    <h1>Weight Tracker</h1>
    <div class="current">
      <span>{{ currentWeight.weight }}</span>
      <small>Current weight in (kg)</small>
    </div>
  </main>
</template>

<style></style>
