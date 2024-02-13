<script setup lang="ts">
import { ref } from "vue"

const periods = ["Today", "This Week", "This Month"] as const;

type Period = typeof periods[number]

const selectedPeriod = ref<Period>("Today");

function selectPeriod(period: Period) {
  selectedPeriod.value = period;
}
</script>

<template>
  <div>
    {{ selectedPeriod }}
    <nav class="is-primary panel">
      <span class="panel-tabs">
        <a v-for="period of periods" :key="period" @click="selectPeriod(period)"
          :class="{ 'is-active': period === selectedPeriod }"> {{ period }}
        </a>
      </span>
    </nav>
  </div>
</template>

<style></style>