<template>
    <div id="scroll-container">
      <section class="services">
        <div ref="service1" class="service">Service 1</div>
        <div ref="service2" class="service">Service 2</div>
        <div ref="service3" class="service">Service 3</div>
      </section>
    </div>
  </template>
  
  <script>
  import { gsap } from "gsap";
  import { ScrollTrigger } from "gsap/ScrollTrigger";
  import Lenis from "@studio-freight/lenis";
  
  gsap.registerPlugin(ScrollTrigger);
  
  export default {
    name: "DummyComponent",
    mounted() {
      // Initialize Lenis for smooth scrolling
      const lenis = new 
      ({
        smooth: true,
        direction: "vertical",
        wrapper: document.querySelector("#scroll-container"),
        content: document.querySelector(".services"),
      });
  
      // Animation frame loop for Lenis
      function raf(time) {
        lenis.raf(time);
        requestAnimationFrame(raf);
      }
      requestAnimationFrame(raf);
  
      // Bind Lenis scroll to ScrollTrigger
      lenis.on("scroll", ScrollTrigger.update);
  
      ScrollTrigger.scrollerProxy("#scroll-container", {
        scrollTop(value) {
          return arguments.length ? lenis.scrollTo(value) : lenis.targetScroll;
        },
        getBoundingClientRect() {
          return {
            top: 0,
            left: 0,
            width: window.innerWidth,
            height: window.innerHeight,
          };
        },
        pinType: document.querySelector("#scroll-container").style.transform ? "transform" : "fixed"
      });
  
      ScrollTrigger.refresh();
  
      // GSAP Animations with ScrollTrigger for horizontal movement and color changes
      gsap.utils.toArray(".service").forEach((service, index) => {
        const timeline = gsap.timeline({
          scrollTrigger: {
            trigger: service,
            start: "top 80%",
            end: "bottom 20%",
            scrub: 1.5,  // Smooth out the scrub for better transition
            scroller: "#scroll-container",
            markers: true,  // Enable markers for debugging
          },
        });
  
        // Animate from left to right with color transitions
        timeline.fromTo(service, 
          { x: index % 2 === 0 ? "-100%" : "100%", opacity: 0 },
          { x: "0%", opacity: 1, backgroundColor: "#ff6347", duration: 1.5, ease: "power2.out" }
        )
        .to(service, 
          { backgroundColor: "#4682b4", duration: 1.5, ease: "power2.inOut" }
        )
        .to(service, 
          { backgroundColor: "#32cd32", duration: 1.5, ease: "power2.inOut" }
        );
  
        // Animate from right to left with color transition reversal
        timeline.to(service, 
          { x: index % 2 === 0 ? "100%" : "-100%", opacity: 0, backgroundColor: "#282c34", duration: 1.5, ease: "power2.in" }
        );
      });
    },
  };
  </script>
  
  <style scoped>
  html,
  body {
    height: 100%;
    overflow: hidden;
  }
  
  #scroll-container {
    height: 100vh;
    overflow: hidden;
    position: relative;
  }
  
  .services {
    height: 300vh; /* Increased height to ensure there's enough scrolling space */
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
  }
  
  .service {
    font-size: 2rem;
    padding: 20px;
    background-color: #282c34;
    color: white;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    margin: 50px 0;
    opacity: 1; /* Start with full opacity */
    transition: background-color 0.5s ease, color 0.5s ease; /* Smooth color transition */
  }
  </style>
  