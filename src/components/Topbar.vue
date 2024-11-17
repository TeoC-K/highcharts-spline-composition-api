<script setup>
import Highcharts from 'highcharts';
import Datepicker from 'vue3-datepicker';
</script>

<template>
  <div class="header">
      <!-- Dropdown for vessel selection --> 
      <div class="vessel-selector">
        <label for="vessel">Data from: </label>
        <select v-model="selectedVessel" @change="updateChart">
          <!--iterate through vessels and display each vessel name in the dropdown-->
          <option v-for="(vessel, index) in vessels" :key="index" :value="vessel.name">
            {{ vessel.name }}
          </option>
        </select>
      </div>

      <!-- Date Pickers for selecting range -->
      <div class="date-picker">
        <label for="start-date">from</label>
        <Datepicker v-model="startDate" id="start-date" />
        <label for="end-date">to</label>
        <Datepicker v-model="endDate" id="end-date" />
        <button @click="applyDateRange">Apply Date Range</button>
      </div>
    </div>
</template>