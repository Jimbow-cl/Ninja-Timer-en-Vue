<script>
export default {
  props: ["score"],
  data() {
    return {
      result: this.score,
      ranking: this.rank(),
    };
  },
  methods: {
    rank() {
      if (this.score <= 300 ) {
        return " Expert";
      }
      if (this.score <= 400 && this.result > 300) {
        return " Intermédiaire";
      } else if (this.score > 400) {
        return " Débutant";
      }
      return "e Erreur de calcul";
    },
  },
}
</script>
<template>
  <div class="block">
    <h1>Votre Score</h1>
    <p>{{ result }} millisecondes</p>
    <p>Vous êtes un{{ ranking }}</p>
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
