<template>
  <div class="computed-properties-exercise container">
    <div class="row">
      <div class="col-12">
        <div class="border p-1">
          <div class="reverse-message">
            <input type="text" v-model="state.myMessage" />
            <p>Original Message: {{ state.myMessage }}</p>
            <p>Computed Reversed Message: {{ state.reversedMessage }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import { computed, reactive } from "vue";
export default {
  name: "computed-properties-exercise",
  setup() {
    const state = reactive({
      // After getting this to work, challenge yourself to add an input field and bind message to it, so as you type the messag gets reversed!
      myMessage: "",
      message: "Hello World!",
      reversedMessage: computed(() => {
        // all computed properties must return a value, what do you want this one to return?
        return state.myMessage.split("").reverse().join("");
      }),
    });
    return {
      state,
    };
  },
};
</script>


<style scoped>
</style>
