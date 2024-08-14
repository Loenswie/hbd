<template>
    <div class="movie">
        <h1 style="text-align: center;">Speciaal filmpje</h1>
        <!--  A mov video in assets called Hloowe.mov-->
        <video width="320" height="240" controls>
            <source src="../assets/Klowie.mp4" type="video/mp4">
        </video>
        <button @click="$router.push('/')">Terug naar de homepagina</button>
    </div>
</template>
  
  <script>
  export default {
    
  };
  </script>
  
  <style scoped>
  .movie {
    font-family: "Happy Monkey", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    padding: 1rem;
  }

  button {
    margin-top: 20px;
    padding: 10px 20px;
    background-color: #4CAF50;
    color: white;
    border: none;
    cursor: pointer;
  }
  </style>
  