<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/gestionnaire-des-tâches-icône.jpg">
    <HelloWorld msg="Bienvenu a l'application de gestion de tâche"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';

export default {
  name: 'Home',
  components: {
    HelloWorld,
  },
};
</script>
