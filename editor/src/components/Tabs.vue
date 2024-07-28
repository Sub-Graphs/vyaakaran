<template>
  <div class="p-4 bg-white rounded shadow-lg">
    <div class="flex justify-around bg-primary text-white rounded-t">
      <button
        class="py-2 px-4 focus:outline-none"
        :class="{ 'bg-primary-light': tab === 'console' }"
        @click="tab = 'console'"
      >
        Console
      </button>
      <button
        class="py-2 px-4 focus:outline-none"
        :class="{ 'bg-primary-light': tab === 'test' }"
        @click="tab = 'test'"
      >
        Test
      </button>
    </div>

    <div class="p-4 bg-gray-100 rounded-b">
      <div v-if="tab === 'console'">
        <Console />
      </div>
      <div v-if="tab === 'test'">
        <Test />
      </div>
    </div>
  </div>
</template>

<script>
import Console from './Console.vue'; // Adjust the path to your component
import Test from './Test.vue'; // Adjust the path to your component

export default {
  components: {
    Console,
    Test,
  },
  data() {
    return {
      tab: 'console', // Initialize with a default value
    };
  },
};
</script>

<style>
.bg-primary {
  background-color: #3f51b5; /* Example primary color */
}

.bg-primary-light {
  background-color: #6573c3; /* Lighter shade for the active tab */
}
</style>
