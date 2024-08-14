<template>
  <div class="home">
    <img alt="Confetti normal" src="../assets/confetti-glitter.gif">
    <img alt="Confetti facing left" src="../assets/confetti-glitter.gif">
  </div>

  <div class="part1">
    <p>
      JAJA, HAPPY BIRTHDAY! 🎉🎉🎉
    </p>
    <p>
      Ik hoop dat je deze mini website leuk vindt! 🎂🎈 Speciaal voor je verjaardag heb ik dit gemaakt om je blij te maken en mijn moeite te showen voor u!
    </p>
    <p>
      Ik hoop dat je een geweldige dag hebt en dat je veel cadeautjes krijgt! 🎁🎁🎁
    </p>

    <img class="pica" alt="Happy Birthday" src="../assets/pica.png">

    <p>
      Birthday girl is SLAYING!
    </p>
  </div>

  <div class="part2">
    <h2 style="padding-bottom: 5rem;">
      <router-link to="/about" class="heading">Ga door naar de bday QUIZ</router-link>
    </h2>
  </div>


  <div class="part4">
    <img alt="Confetti normal" src="../assets/happy-birthday-the-office.gif">
  </div>
  <!--
  <div class="part3">
    <h2 style="padding-top: 5rem;">
      Guestbook
    </h2>


  </div>


  <div class="part5">
    <h2 style="padding-top: 5rem;">
      <router-link to="/filmpje">Speciaal filmpje</router-link>
    </h2>
  </div>
  -->
</template>

<script>

export default {
  name: 'HomeView',
  components: {
  }
}
</script>
<style scoped>
.home {
  font-family: "Happy Monkey", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100%;
  display: flex;
  justify-content: space-between;
  text-align: center;
}

.part1 {
  font-family: "Happy Monkey", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 1rem;
}

.part2 .heading {
  padding: 1rem;
  background-color: #f1c40f;
  border-radius: 1rem;
}

img {
  width: 40%;
  height: auto;
  padding: 1rem;
}

img:nth-child(2) {
  transform: rotate(270deg);
}

p {
  font-size: 1.5rem;
  padding: 1rem;
}

.pica {
  width: 100%;
  height: auto;
}




</style>

