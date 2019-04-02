<template>
  <v-container>
    <v-layout>
      <v-flex xs12 sm8 md6 offset-sm2 offset-md3 text-xs-center>
        <v-avatar size="200">
          <v-img
            class="elevation-6"
            src="/img/photo.jpg"
            aspect-ratio="1"
          ></v-img>
        </v-avatar>
        <div class="body-1 mt-5">
          <p>
            Hi! I'm José Coelho, a Portuguese MSc student of
            <a
              href="https://fenix.tecnico.ulisboa.pt/cursos/meec"
              target="_blank"
              >Electrical Engineering and Computer Science</a
            >
            at
            <a href="https://tecnico.ulisboa.pt/en/" target="_blank"
              >Técnico Lisboa</a
            >. Currently I'm working on my MSc Thesis on
            <span class="body-2"
              >Feature Selection for Early Prediction In Multivariate Time
              Series</span
            >.
          </p>
          <p>
            I'm also a Software Engineer at
            <a href="https://www.premium-minds.com/" target="_blank"
              >Premium Minds</a
            >, a portuguese software house.
          </p>

          <p>
            Previously I was the president of
            <a href="https://neecist.org/" target="_blank">NEECIST</a>, a
            students group at my University.
          </p>
        </div>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: "AboutResume"
};
</script>
