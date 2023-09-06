<script>
export default {
  name: "BlockVue",
  props: ["delay"],
  mounted() {
    console.log("mounted");
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
      console.log(this.delay);
    }, this.delay);
  },
  updated() {
    console.log("updated");
  },
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0,
    };
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
      console.log(this.reactionTime);
      /* permet d'envoyer un custom event à un composant parent. 
      *Ici, on envoie le temp de réaction à l'app.vue*/ 
      this.$emit("reactionTime", this.reactionTime);
    },
  },
};
</script>

<template>
  <div class="block" v-if="showBlock" @click="stopTimer">Click Me</div>
</template>

<style scoped>
.block {
  width: 400px;
  color: white;
  font-size: 30px;
  border-radius: 20px;
  background: #0faf87;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>
