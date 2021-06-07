<template>
  <v-app dark>
    <v-main>
      <nuxt />
    </v-main>
  </v-app>
</template>

<script>
export default {};
</script>

<style>
html {
  scroll-behavior: smooth;
}
/* width */
::-webkit-scrollbar {
  width: 8px;
}

/* Track */
::-webkit-scrollbar-track {
  background: rgba(0, 0, 0, 0.2);
}

/* Handle */
::-webkit-scrollbar-thumb {
  background: #888;
  -webkit-border-radius: 8px;
}

/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #555;
}
</style>
