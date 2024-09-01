<template>

   
    <div class="box1" ref="box1">Animate Me!</div>
    <div class="box2" ref="box2">Animate Me!</div>
    <!-- Dummy content to ensure scrolling -->
    <div style="height: 100vh;"></div>

  </template>
  
  <script>
  import { gsap } from "gsap";
  import { ScrollTrigger } from "gsap/ScrollTrigger";
  
  // Register the ScrollTrigger plugin with GSAP
  gsap.registerPlugin(ScrollTrigger);
  
  export default {
    mounted() {
      gsap.to(".box1", {
        x: 200,
        rotation: 360,
        duration: 3,
        scrollTrigger: {
          trigger: ".box1", // The element that triggers the animation
          toggleActions: "play none none none",
          markers: true, // Add markers to the scrollbar for debugging
          start: "top 70%", // Start the animation when the top of the element is at the center of the viewport
          end: "top 200px", // End the animation when the top of the element reaches 100px from the top of the viewport
          scrub: true, // Smoothly scrubs the animation in sync with the scrollbar movement
          pin: ".box2", // Pin the element in place while the animation is active
        },
      });
    },
  };
  </script>
  
  <style scoped>
  .box1 {
    width: 100px;
    height: 100px;
    background-color: red;
  }
  .box2 {
    width: 100px;
    height: 100px;
    background-color: green;
  }
  </style>
  