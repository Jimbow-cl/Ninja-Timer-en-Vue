<script>
export default {
  props:['score'],
  data() {
    return {
    result: this.score,
    };
  },
  methods: {},
};
</script>
<template>
  <div class="block">
    <h1>Votre Score</h1>
    <p>{{ result }} millisecondes</p>
  </div>
</template>
<style scoped>
.block {
  width: 400px;
  color: white;
  font-size: 30px;
  border-radius: 20px;
  background: coral;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>
