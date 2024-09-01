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
    </div>
    <div class="block1b">
      <h1>Design <br> Transform <br>
         Accelerate</h1> <br>
      <h5>We Revolutionize User Experience <br>
        Using Behavioural Science.</h5>
    </div>
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
      <div class="circle_red"></div>
    </div>
    <div class="line"></div>
    <div class="circle_big"></div>
    <div class="line"></div>
    <div class="circle_small">
      <div class="circle_blue"></div>
    </div>
  </div>
  <div class="heading">
    <div class="circle_dot">
      <div class="circle_red"></div>
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
      <div class="circle_blue"></div>
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
      <div class="circle_purple"></div>
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

<script></script>

<style scoped>
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
.menu_bar ul li {
  display: inline;
  padding: 0 20px;
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
.menu_bar a {
  text-decoration: none;
  color: black;
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

.opt1 {
  width: 350px;
  height: 150px;
  background-color: #fcc4d1;
  text-align: center;
  font-size: 40px;
  border-radius: 10px;
}
.opt2 {
  width: 350px;
  height: 150px;
  background-color: #b8b8fd;
  text-align: center;
  font-size: 40px;
  border-radius: 10px;
}
.opt3 {
  width: 350px;
  height: 150px;
  background-color: #d4b1f1;
  text-align: center;
  font-size: 40px;
  border-radius: 10px;
}
header {
  position: sticky;
  top: 0;
  background-color: white;
  margin-bottom: 5%;
}

/*--------------------------------------------------------------------- */
.block1{
  display: flex;
  gap: 2%;
  margin: auto;
  width: 55%;
  padding: 15px;
}
.block1a{
  width: 50%;
  height: 320px;
  background-color: #f1f1f1;
  
}
.block1b{
  width: 50%;
  height: 300px;
  padding: 15px;
}
.block1b h1{
  font-size: 75px;
  font-weight: 1200;
 line-height: 70px;
}
.block1b h5{
  font-size: 20px;
  font-weight: 400;
}
.brands_name{
  display: flex;
  gap: 7%;
  margin: 3% auto;
  width: 55%;
  padding: 15px;
}
.contnt{
  width: 55%;
  margin: 3% auto;
  padding: 15px;
  font-size: 25px;
  font-weight: 1200;
  line-height: 50px;
  word-spacing: 10px;
}
.circle_div{
  display: flex;
  margin: 3% auto;
  width: 55%;
}
.circle_small{
  width: 90px;
  height: 90px;
  border: 1px solid black;
  border-radius: 50%;
  margin-top: 35px;
  box-shadow: -10px 7px 0 0 black;
}
.line{
  width: 200px;
  height: 1px;
  background-color: black;
  margin-top: 75px;
}
.circle_big{
  width: 150px;
  height: 150px;
  border: 1px solid black;
  border-radius: 50%;
  box-shadow: -10px 7px 0 0 black;
}
.circle_red{
  width: 60px;
  height: 60px;
  background-color: #FB5457;
  border-radius: 50%;
  margin: 15px 15px;
}
.circle_blue{
  width: 60px;
  height: 60px;
  background-color: #5857F9;
  border-radius: 50%;
  margin: 15px 15px;
}
.circle_purple{
  width: 60px;
  height: 60px;
  background-color: #9C34F0;
  border-radius: 50%;
  margin: 15px 15px;
}
.heading{
  display: flex;
  gap: 2%;
  margin: 6% auto 0;
  width: 55%;
}
.heading h1{
  font-size: 60px;
  font-weight: 1200;
  line-height: 60px;
  margin-top: 45px;
  margin-left: 15px;
  margin-right: 15px;
  margin-bottom: 35px;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 
  'Open Sans', 'Helvetica Neue', sans-serif;
}
.circle_dot{
  width: 90px;
  height: 90px;
  border: 1px dashed black;
  border-radius: 50%;
  margin-top: 35px;
}
.content{
  width: 55%;
  margin: -20px auto 0;
  padding: 15px 45px;
  font-size: 20px;
  font-weight: 1200;
  word-spacing: 10px;
}
.content ul li{
  list-style-type: none;
  margin: 5px 10%;
}

</style>
