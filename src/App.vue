<template>
  <div class="bg-blue-50 min-h-screen">
    <div class="container mx-auto">
      <header class="flex justify-center items-center text-3xl h-32 mx-5">
        いいねした画像を並べるサイト
      </header>
      <div class="flex justify-center">
        <MainTable />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import MainTable from "./components/MainTable.vue";

export default defineComponent({
  name: "Home",
  components: {
    MainTable,
  },
});
</script>
