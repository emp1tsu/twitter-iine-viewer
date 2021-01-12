<template>
  <div>
    <InputForm @on-submit="handleSubmit" />
    <div class="box h-64 text-center m-5 p-4">
      {{ state.message }}
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive } from "vue";
import InputForm from "./InputForm.vue";

export default defineComponent({
  name: "MainTable",
  components: { InputForm },
  setup() {
    const state = reactive({
      message: "",
    });

    const handleSubmit = (screenName: string) => {
      state.message = "done";
      console.log({ screenName });
    };

    return {
      state,
      handleSubmit,
    };
  },
});
</script>
<style></style>
