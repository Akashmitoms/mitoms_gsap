<template>
  <header>
    <div class="head">
      <div class="logo">
        <img src="/image/Logo-01.png" alt="Logo" />
      </div>
      <div class="menu_bar">
        <ul class="animated-link">
          <li><a>Work</a></li>
          <li class="dropdown">
            <a href="#"
              >Services <span class="icon"><fa icon="circle" /></span
            ></a>
            <div class="dropdown-content">
              <div class="opt1">Design</div>
              <div class="opt2">Technology</div>
              <div class="opt3">Marketing</div>
            </div>
          </li>

          <li><a href="">Clients</a></li>
          <li class="dropdown">
            <a href=""
              >About
              <span class="icon"><fa icon="circle" /></span>
            </a>
            <div class="dropdown-content">
              <div class="opt1">About Us.</div>
              <div class="opt2">Team.</div>
              <div class="opt3">Career.</div>
            </div>
          </li>
          <li><a href="">Knowledge</a></li>
          <li><fa icon="toggle-on" /></li>
          <li><button>Contact</button></li>
        </ul>
      </div>
    </div>
    <hr />
  </header>

  <div class="block1">
    <div class="block1a">
      <h1>Image box</h1>
      <!-- SVG Animation Container -->
      <div class="svg-container">
        <svg id="morphing-svg" width="300" height="300" viewBox="0 0 300 300" xmlns="http://www.w3.org/2000/svg">
          <path
            id="morphing-path"
            d="M150 150 m -100, 0 a 100,100 0 1,0 200,0 a 100,100 0 1,0 -200,0"
            fill="#5857F9"
          />
          <text id="svg-text" x="50%" y="55%" text-anchor="middle" fill="#fff" font-size="40" font-family="Arial, sans-serif">
            Mitoms
          </text>
        </svg>
      </div>
    </div>
    <div class="block1b">
      <h1>
        Design <br />
        Transform <br />
        Accelerate
      </h1>
      <br />
      <h5>
        We Revolutionize User Experience <br />
        Using Behavioural Science.
      </h5>
    </div>
  </div>

  <div class="moving-circles">
    <div ref="redCircle" class="small-circle red-circle"></div>
    <div ref="blueCircle" class="small-circle blue-circle"></div>
    <div ref="purpleCircle" class="small-circle purple-circle"></div>
  </div>



  <div class="brands_name">
    <img src="/image/Logo02.png" height="60px" alt="">
   <img src="/image/Logo-Final-avanika.png" width="60px" height="60px" alt="">
    <img src="/image/Logo04.png" height="60px" alt="">
    <h1 style="font-family: Verdana, Geneva, Tahoma, sans-serif; font-size: 50px;">MVTL</h1>
  </div>

  <div class="contnt"><h2>We are a global creative agency that <br> 
  combines design expertise with technology <br> and intelligence.</h2></div>

  <div class="circle_div">
    <div class="circle_small">
      <div ref="circle_red" class="circle_red"></div>
    </div>
    <div class="line"></div>
    <div class="circle_big"></div>
    <div class="line"></div>
    <div class="circle_small">
      <div ref="circle_blue" class="circle_blue"></div>
    </div>
  </div>
  <div class="heading">
    <div class="circle_dot">
      <div  ref="circle_red" class="circle_red"></div>
    </div>
    <h1>Design</h1>
  </div>
<div class="content">
  <ul>
    <li>UI Design</li>
    <li>UX Design</li>
    <li>UX Consultancy</li>
    <li>Design System</li>
    <li>Animation</li>
    <li>Illustrations</li>
  </ul>
</div>
<div class="heading">
    <div class="circle_dot">
      <div ref="circle_blue" class="circle_blue"></div>
    </div>
    <h1>Technology</h1>
  </div>
<div class="content">
  <ul>
    <li>Web Design</li>
    <li>Softwares</li>
    <li>Mobile Apps</li>
    <li>Web Apps</li>
    <li>Front-End</li>
    <li>Back-End</li>
  </ul>
</div>
<div class="heading">
    <div class="circle_dot">
      <div ref="circle_purple" class="circle_purple"></div>
    </div>
    <h1>Business</h1>
  </div>
<div class="content">
  <ul>
    <li>Branding</li>
    <li>Brand Name</li>
    <li>Brand Guidelines</li>
    <li>Strategy</li>
    <li>Digital Marketing</li>
    <li>S.E.O</li>
  </ul>
</div>
<div class="contnt">
  <h2>As global leaders in UX UI, technology, and <br> 
    business solutions, we partner with clients <br> 
    to simplify, strengthen, and transform their <br> 
    businesses.</h2>
</div>
</template>

<script>
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';
import Lenis from '@studio-freight/lenis';

gsap.registerPlugin(ScrollTrigger);

export default {
  mounted() {
    // Initialize Lenis for smooth scrolling
    const lenis = new Lenis({
      duration: 1.2,
      easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t)),
    });

    function raf(time) {
      lenis.raf(time);
      requestAnimationFrame(raf);
    }

    requestAnimationFrame(raf);

    // Access the elements using refs
    const redDiv = this.$refs.circle_red;
    const blueDiv = this.$refs.circle_blue;
    const purpleDiv = this.$refs.circle_purple;

    const movingRedCircle = this.$refs.redCircle;
    const movingBlueCircle = this.$refs.blueCircle;
    const movingPurpleCircle = this.$refs.purpleCircle;

    // Set the divs to have a transparent background color by default
    gsap.set([redDiv, blueDiv, purpleDiv], { backgroundColor: 'transparent' });

    // Function to get the absolute position of an element
    const getPosition = (element) => {
      const rect = element.getBoundingClientRect();
      return {
        x: rect.left + window.scrollX,
        y: rect.top + window.scrollY,
      };
    };

    // Create an animation for each circle
    const createAnimation = (movingCircle, targetDiv, color) => {
      gsap.to(movingCircle, {
        x: () => getPosition(targetDiv).x - getPosition(movingCircle).x + (targetDiv.offsetWidth / 2) - (movingCircle.offsetWidth / 2),
        y: () => getPosition(targetDiv).y - getPosition(movingCircle).y + (targetDiv.offsetHeight / 2) - (movingCircle.offsetHeight / 2),
        scrollTrigger: {
          trigger: targetDiv,
          start: 'top 80%',
          end: 'top 20%',
          scrub: true,
          onEnter: () => {
            gsap.to(targetDiv, { backgroundColor: color, duration: 0.5 });
            gsap.to(movingCircle, { opacity: 0, duration: 0.5 });
          },
          onLeave: () => {
            gsap.to(targetDiv, { backgroundColor: 'transparent', delay: 0.5, duration: 0.5 });
            gsap.to(movingCircle, { opacity: 1, duration: 0.5 });
          },
          onEnterBack: () => {
            gsap.to(targetDiv, { backgroundColor: color, duration: 0.5 });
            gsap.to(movingCircle, { opacity: 0, duration: 0.5 });
          },
          onLeaveBack: () => {
            gsap.to(targetDiv, { backgroundColor: 'transparent', delay: 0.5, duration: 0.5 });
            gsap.to(movingCircle, { opacity: 1, duration: 0.5 });
          },
          markers: true, // Optional: Add markers to debug
        },
      });
    };

    // Create animations for each circle and div
    createAnimation(movingRedCircle, redDiv, '#FB5457');
    createAnimation(movingBlueCircle, blueDiv, '#5857F9');
    createAnimation(movingPurpleCircle, purpleDiv, '#9C34F0');

    // Additional logic for circle_div matching color divs
    const circleDivs = document.querySelectorAll('.circle_div .circle_small > div');
    circleDivs.forEach((circleDiv, index) => {
      let movingCircle, color;

      if (circleDiv === redDiv) {
        movingCircle = movingRedCircle;
        color = '#FB5457';
      } else if (circleDiv === blueDiv) {
        movingCircle = movingBlueCircle;
        color = '#5857F9';
      } else if (circleDiv === purpleDiv) {
        movingCircle = movingPurpleCircle;
        color = '#9C34F0';
      }

      if (movingCircle && color) {
        createAnimation(movingCircle, circleDiv, color);
      }
    });
  },
};



</script>







<style scoped>
/* General Styles */
body {
  margin: 0;
  padding: 0;
  font-family: Arial, sans-serif;
}

header {
  position: sticky;
  top: 0;
  background-color: white;
  margin-bottom: 5%;
}

.head {
  display: flex;
  align-items: center;
  padding: 1%;
}

.logo {
  width: 70%;
}

.logo img {
  margin-left: 50%;
  width: 200px;
}

.menu_bar {
  width: 100%;
}

.menu_bar ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  gap: 20px;
}

.menu_bar ul li {
  display: inline;
}

.menu_bar ul li a {
  text-decoration: none;
  color: black;
}

.menu_bar button {
  padding: 12px 25px;
  border-radius: 5px;
  color: white;
  background-color: black;
}

.icon {
  font-size: 9px;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: white;
  max-width: 100%;
  padding: 12px 16px;
  z-index: 1;
  margin-left: -20%;
}

.dropdown:hover .dropdown-content {
  display: flex;
  gap: 2%;
}

.opt1,
.opt2,
.opt3 {
  width: 350px;
  height: 150px;
  text-align: center;
  font-size: 40px;
  border-radius: 10px;
}

.opt1 {
  background-color: #fcc4d1;
}

.opt2 {
  background-color: #b8b8fd;
}

.opt3 {
  background-color: #d4b1f1;
}

/* Block Section */
.block1 {
  display: flex;
  gap: 2%;
  margin: auto;
  width: 55%;
  padding: 15px;
}

.block1a {
  width: 50%;
  height: 320px;
  background-color: #f1f1f1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  position: relative;
}

.block1b {
  width: 50%;
  height: 300px;
  padding: 15px;
}

.block1b h1 {
  font-size: 75px;
  font-weight: 1200;
  line-height: 70px;
}

.block1b h5 {
  font-size: 20px;
  font-weight: 400;
}

/* Brands Section */
.brands_name {
  display: flex;
  gap: 7%;
  margin: 3% auto;
  width: 55%;
  padding: 15px;
}

.brands_name img {
  height: 60px;
}

.brands_name h1 {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-size: 50px;
}

.contnt {
  width: 55%;
  margin: 3% auto;
  padding: 15px;
  font-size: 25px;
  font-weight: 1200;
  line-height: 50px;
  word-spacing: 10px;
}

/* Circle Div Section */
.circle_div {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100vh; /* Full viewport height */
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.circle_small {
  width: 90px;
  height: 90px;
  border: 1px solid black;
  border-radius: 50%;
  margin-top: 35px;
  box-shadow: -10px 7px 0 0 black;
}

.line {
  width: 200px;
  height: 1px;
  background-color: black;
  margin-top: 75px;
}

.circle_big {
  width: 150px;
  height: 150px;
  border: 1px solid black;
  border-radius: 50%;
  box-shadow: -10px 7px 0 0 black;
}

.circle_red,
.circle_blue,
.circle_purple {
  width: 60px;
  height: 60px;
  background-color: transparent;
  border-radius: 50%;
  margin: 15px 15px;
  transition: background-color 0.5s ease, opacity 0.5s ease;
}

/* Heading and Content */
.heading {
  display: flex;
  gap: 2%;
  margin: 6% auto 0;
  width: 55%;
}

.heading h1 {
  font-size: 60px;
  font-weight: 1200;
  line-height: 60px;
  margin-top: 45px;
  margin-left: 15px;
  margin-right: 15px;
  margin-bottom: 35px;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

.circle_dot {
  width: 90px;
  height: 90px;
  border: 1px dashed black;
  border-radius: 50%;
  margin-top: 35px;
}

.content {
  width: 55%;
  margin: -20px auto 0;
  padding: 15px 45px;
  font-size: 20px;
  font-weight: 1200;
  word-spacing: 10px;
}

.content ul li {
  list-style-type: none;
  margin: 5px 10%;
}

/* Moving Circles */
.circle-container {
  position: relative;
  width: 100px;
  height: 100px;
  margin: 0 auto;
}

.circle {
  position: absolute;
  width: 50px;
  height: 50px;
  border-radius: 50%;
}

.red-circle {
  background-color: #fb5457;
}

.blue-circle {
  background-color: #5857f9;
}

.purple-circle {
  background-color: #9c34f0;
}

.svg-container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 20px;
  width: 300px;
  height: 300px;
}

.moving-circles {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  flex-direction: row;
  gap: 20px;
  z-index: 10;
}

.small-circle {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  transition: transform 0.3s ease, opacity 0.3s ease;
}

.red-circle {
  background-color: #fb5457;
  opacity: 1;
}

.blue-circle {
  background-color: #5857f9;
  opacity: 1;
}

.purple-circle {
  background-color: #9c34f0;
  opacity: 1;
}

.circle_red,
.circle_blue,
.circle_purple {
  transition: background-color 0.5s ease, opacity 0.5s ease;
  background-color: transparent; /* Ensure transparent background by default */
}


</style>
