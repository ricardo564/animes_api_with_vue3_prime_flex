<template>
  <h1 class="text-primary">Whispers From The Abyss</h1>
  <div class="cursor-pointer">
    <Carousel :value="cars">
      <template #item="slotProps">
        <Card class="m-1" v-for="(anime, index) in animes" :key="index">
          <template #title>
            <div class="p-card-title text-primary">
              {{ anime.anime }}
            </div>
          </template>
          <template #content>
            <div class="p-card-content">
              {{ anime.quote }}
            </div>
          </template>
          <template #footer>
            <div class="p-card-footr text-primary">
              {{ anime.character }}
            </div>
          </template>
        </Card>
      </template>
    </Carousel>
  </div>
</template>

<script>
import Carousel from 'primevue/carousel';
import Card from "primevue/card";
import axios from "axios";


export default {
  name: "AnimesList",
  components: {
    Card,
  },
  data() {
    return {
      animes: [],
    };
  },
  created() {
    axios
      .get("https://animechan.vercel.app/api/quotes")
      .then(({ data }) => {
        this.animes = data;
        console.log(this.animes);
        console.log(this.animes[0]);
      })
      .catch((error) => {
        console.log(error);
      });
  },
};
</script>

<!-- CSS  -->