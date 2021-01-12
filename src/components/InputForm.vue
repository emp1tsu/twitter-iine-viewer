<template>
  <div>
    <form @submit.prevent="handleSubmit">
      <div class="flex justify-center mb-5 mx-5">
        <p class="md-5">
          twitterのスクリーンネームを入力してください（例：@emp1tsu1）
          <br />
          <br />
          その人がいいねした画像が良い感じに表示されます。
        </p>
      </div>
      <div class="flex mb-5 mx-auto max-w-xs">
        <div class="mt-1 relative rounded-md shadow-sm mx-5 w-11/12">
          <div
            class="absolute inset-y-0 left-0 pl-3 flex items-center pointer-events-none"
          >
            <span class="text-gray-500 sm:text-sm">@</span>
          </div>
          <input
            type="text"
            autoCapitalize="off"
            name="screenName"
            v-model="state.screenName"
            @input="handleChange"
            class="bg-white focus:outline-none focus:shadow-outline py-2 px-8 rounded-md w-full"
          />
        </div>
      </div>
      <div class="flex justify-center mb-5 mx-5">
        <input
          type="submit"
          value="取得"
          :disabled="this.state.screenName === ''"
          class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-2 mx-2 rounded w-20 mb-10"
        />
      </div>
    </form>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive } from "vue";

type InputEvent = {
  target: { value: string };
};

export default defineComponent({
  name: "InputForm",
  components: {},
  setup(props: {}, { emit }) {
    const state = reactive({
      screenName: "",
    });

    const handleSubmit = () => {
      emit("on-submit", state.screenName);
    };

    const handleChange = (event: InputEvent) => {
      state.screenName = event.target.value;
    };

    return {
      state,
      handleSubmit,
      handleChange,
    };
  },
});
</script>
<style></style>
