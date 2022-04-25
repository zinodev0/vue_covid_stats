<template>
  <div class="grid md:grid-cols-3 gap-4">
    <div class="shadow-md bg-blue-100 p-10 text-center rounded">
      <h3 class="text-3xl text-blue-900 font--bold mb-4">Cases</h3>
      <div class="text-2xl mb-4">
        <span class="font-bold">New:</span>
        {{ formattedNumbers(stats.NewConfirmed) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ formattedNumbers(stats.TotalConfirmed) }}
      </div>
    </div>
    <!-- Box 2 -->
    <div class="shadow-md bg-green-100 p-10 text-center rounded">
      <h3 class="text-3xl text-green-900 font--bold mb-4">Recovered</h3>
      <div class="text-2xl mb-4">
        <span class="font-bold">New:</span>
        {{ formattedNumbers(stats.NewRecovered) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ formattedNumbers(stats.TotalRecovered) }}
      </div>
    </div>
    <!-- box 3 -->
    <div class="shadow-md bg-red-100 p-10 text-center rounded">
      <h3 class="text-3xl text-red-900 font--bold mb-4">Deaths</h3>
      <div class="text-2xl mb-4">
        <span class="font-bold">New:</span>
        {{ formattedNumbers(stats.NewDeaths) }}
      </div>
      <div class="text-2xl mb-4">
        <span class="font-bold">Total:</span>
        {{ formattedNumbers(stats.TotalDeaths) }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DataBoxes",
  props: ["stats"],
  methods: {
    formattedNumbers(x) {
      return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
    },
  },
};
</script>
