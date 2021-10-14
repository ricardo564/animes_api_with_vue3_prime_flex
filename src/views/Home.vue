<template>
  <div>
    <AnimesList msg="Welcome.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import AnimesList from "@/components/Animes_List.vue";

export default {
  name: "Home",
  components: {
    AnimesList,
  },
};
</script>
