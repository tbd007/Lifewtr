<template>
  <div class="wrapper">
  
  <div class="main">
  
    <transition-group name="fade" tag="div">
      <div class="slidewrap" v-for="i in [currentIndex]" :key="i">
        <img :src="currentImg" />
      </div>
    </transition-group>
   

  </div>
  <div class="txt">
  
  <img class="logo" src="/assets/logo.jpg"/>
  <div class="info">
  <h1>LIFEWTR: THIRST INSPIRATION</h1>
  <h3>LIFEWTR launched in January 2017 as PepsiCo's purpose-driven, premium water brand, 'existing to advance and showcase sources of creation and creativity' and commitment to the belief that 'Art Makes Life More Inspired'. The idea is that inspiration is as essential to life as water.

Through each emerging artist's story, LIFEWTR raised awareness around various cultural anchors relevant to society today, i.e. Public Art, Women in Art, Fashion is Art, and Arts in Education, all while communicating LIFEWTR's involvement and support in each cultural category.</h3>
  </div>
  <button class="btn"><a href="https://lifewtr.com/en-us/home">GET INSPIRED</a></button>
  <img class="hand" src="/assets/hand.png"/>
  </div>
  </div>
</template>
<script>
export default {
  name: "Slider",
  data() {
    return {
      images: [
    
        "/assets/lifewater2.jpg",
        "/assets/lifewater3.png",
        "/assets/lifewater4.jpg"
       
      ],
      timer: null,
      currentIndex: 0
    };
  },

  mounted: function() {
    this.startSlide();
  },

  methods: {
    startSlide: function() {
      this.timer = setInterval(this.next, 4000);
    },

    next: function() {
      this.currentIndex += 1;
    },
    prev: function() {
      this.currentIndex -= 1;
    }
  },

  computed: {
    currentImg: function() {
      return this.images[Math.abs(this.currentIndex) % this.images.length];
    }
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Allura&family=Dancing+Script:wght@500&family=Montserrat&display=swap');
.fade-enter-active,
.fade-leave-active {
  transition: all 0.9s ease;
  overflow: hidden;
  visibility: visible;
  position: absolute;
  width:50vw;
  opacity: 1;
}

h1{
line-height:2.1rem;
font-size:28px;
}

h3{
color:white;
font-family:'Montserrat';
font-size:12px;
font-weight:300;
text-align:justify;
}

.hand{
position:absolute;
top:7%;
right:30%;
z-index:1;
width:250px;
height:auto;
}

.fade-enter,
.fade-leave-to {
  visibility: hidden;
  width:50vw;
  opacity: 0;
}

img {
  height:80vh;
  width:auto;
  margin-top:10px;
}

.main, .slidewrap{
width:50vw;
padding-top:20px;
}

.btn {
font-size:16px;
font-family:'Montserrat';
color:black;
letter-spacing:0.2rem;
padding:13px 15px;
border:none;
background:palevioletred;
box-shadow: 2px -2px 5px black, 0px 2px 5px darkgray;
text-decoration:none;
margin-left:170px;
margin-top:-19px;
z-index:3;
}

.btn:hover{
border:1px solid black;
}

a{
text-decoration:none;
color:black;
border:none;
font-weight:600;
text-shadow:1px 1px 1px palevioletred;
}

.prev, .next {
  cursor: pointer;
  position: absolute;
  top: 40%;
  width: auto;
  padding: 16px;
  color: white;
  font-weight: bold;
  font-size: 18px;
  transition: 0.7s ease;
  border-radius: 0 4px 4px 0;
  text-decoration: none;
  user-select: none;
}

.next {
  right: 0;
}

.logo{
position:absolute;
top:-1.2%;
right:48%;
height:100px;
width:auto;
}

.txt{
background:linear-gradient(100deg, white, white, rgba(209, 102, 139, 0.26), rgba(209, 102, 139, 0.33), rgba(54, 42, 70, 0.44));
background-size:cover;
width:99%;
padding:50px;
display:flex;
flex-direction:column;
justify-content:flex-start;
align-items:center;
color:white;
text-shadow:2px 2px 2px rgba(0, 0, 0, 0.78);
line-height:1.3em;

}

.wrapper{
width:90%;
display:grid;
grid-template-rows:95vh;
margin-top:10px;
grid-template-columns: 49% 49%;
overflow:hidden;
border:7px solid black;
margin:0 auto;
}

.info{
width:60%;
height:auto;
background:rgba(0, 0, 0, 0.95);
margin-top:85px;
padding:15px 25px;
box-shadow: 3px 2px 10px black;
line-height:1.3rem;
z-index:2;
}

.prev {
  left: 0;
}

.prev:hover, .next:hover {
  background-color: rgba(0,0,0,0.9);
}

@media (max-width:768px){
.wrapper {
grid-template-rows: 99vh auto;
grid-template-columns:auto;
}
img{
height:300px;
margin-top:50px;
width:auto;
}
.hand{
top:70%;
left:50%;
width:180px;
}
.info{
width:78%;
margin:0 auto;
margin-top:0px;
margin-left:5px;
box-shadow:none;
}
.txt{
padding:5px;
background:none;
margin-top:-30px;
padding-bottom:40px;
}
.btn {
margin-left:100px;
font-size:14px;
}
.logo{
top:-9%;
left:36%;
}
.fade-enter-active,
.fade-leave-active {
  transition: all 0.9s ease;
  overflow: hidden;
  visibility: visible;
  position: absolute;
  width:45vw;
  opacity: 1;
}
.fade-enter,
.fade-leave-to {
  visibility: hidden;
  width:45vw;
  opacity: 0;
}
}
</style>
