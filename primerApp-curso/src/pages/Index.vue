<template>
  <q-page padding>
    <button style="position: absolute; right: 15px" @click="count++">
      {{ count }}
    </button>

    <!-- <input
      v-model="message"
      @keyup.esc="clearMessage"
      @keyup.enter="alertMessage"
      @mouseenter="alertMessage"
      @mouseleave="clearMessage"
    /> -->
    <input
      v-model="message"
      @keyup.esc="clearMessage"
      @keyup.enter="alertMessage"
    />

    <button @click="message = ''">Clear</button>

    <!-- <h5 v-show="message.length" class="my-border">{{ message }}</h5> -->
    <h5 v-if="message.length" class="my-border">{{ message }}</h5>
    <h6 v-else>No messages to show</h6>

    <hr />

    <p>Uppercase message: {{ messageUppercase }}</p>

    <p>Lowercase message: {{ message | messageLowercase }}</p>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  data() {
    return {
      message: "Un mensaje para Vue JS ",
      count: 0,
    };
  },
  computed: {
    messageUppercase() {
      console.log("messageUppercase was fired ");
      return this.message.toUpperCase() + this.count;
    },
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
  filters:{
    messageLowercase(value){
      return value.toLowerCase();
    }
  }
});
</script>
<style>
.my-border {
  border: 1px solid brown;
}
</style>
