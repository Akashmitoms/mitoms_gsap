<template>
  <v-app>
    <v-main>
      <Home />
      <DummyComponent />
      <!-- <DummyComponentII /> -->
    </v-main>
  </v-app>
</template>

<script >
import { gsap } from "gsap";
  import { ScrollTrigger } from "gsap/ScrollTrigger";
  export default {
    name: "App",
    components: {
      Home: () => import("./components/Home.vue"),
      DummyComponent: () => import("./components/DummyComponent.vue"),
      // DummyComponentII: () => import("./components/DummyComponentII.vue"),
    },
    mounted() {
      gsap.registerPlugin(ScrollTrigger);
      
    },
  };
</script>
