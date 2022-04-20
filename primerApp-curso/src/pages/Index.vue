<template>
  <q-page padding>
    <input
      v-model="message"
      @keyup.esc="clearMessage"
      @keyup.enter="alertMessage"
      @mouseenter="alertMessage"
      @mouseleave="clearMessage"
    />
    <button @click="message = ''">Clear</button>
    <h5 class="my-border" v-show="message.length" >{{ message }}</h5>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  data() {
    return {
      message: "Un mensaje para Vue JS",
    };
  },
  methods: {
    clearMessage() {
      this.message = "";
    },
    /* handleKeyup(e) {
      console.log(e);
      if (e.keyCode == 27) {
        this.clearMessage();
      } else if (e.keyCode == 13) {
        this.alertMessage();
      }
    }, */
    alertMessage() {
      alert(this.message);
    },
  },
});
</script>
<style>
  .my-border{
    border: 1px solid brown;
  }
</style>
