<template>
  <img src="..\assets\circle.jpg" 
  id="circle" style="width:100px; height:100px; top:122 left:122" @click="move"
  draggable="false">
<div style="position:absolute; bottom: 0px; left: 0px">
<p style="font-size:40px; color:white" id ="p1">
 0
</p>
</div>
</template>

<script>
export default {
data() {
  return {
    counter: 0
  };
},
methods: {
  move(){
      const d = document.getElementById("circle");
      d.style.position="absolute";
      d.style.top=`${Math.random()*85}%`;
      d.style.left=`${Math.random()*85}%`;
      this.counter += 1;
      document.getElementById("p1").innerHTML = this.counter;
  }
},
// mounted() {
//   this.counter = 0
// }
};
</script>


<style>
body {
        background-color: black;
        background-repeat: no-repeat;
        background-size: cover;
        }
</style>