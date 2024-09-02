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
  