<template>
    <div class="container">
        <div class="row">
           <h3>Your Feedback is important for us</h3>
            <form>
                <div  class="row">
                    
                    <label  for="name">Tell us Somthing about you :     </label>
                    
                    <input type="text"   v-model="about" placeholder="Discribe your self"/>
                    <div v-if="about!==''" class="box">
                        <img id="boss" src="../assets/face.gif" alt="game1"/>
                        {{about}}</div>
                    
                </div>
                <div v-if="like==true" class="row">
                    
                    <label  for="name">Why do you like about this :     </label>
                    
                    <input type="text"   v-model="feed" placeholder="We need your feedback"/>
                     <div v-if="feed!==''" class="box">
                        <img id="iron" src="../assets/giphy.gif" alt="game1"/>
                        {{feed}}</div>
                    
                </div>
                <div v-if="like===false" class="row">
                    
                    <label  for="name">Any recommendation for us  :     </label>
                    
                    <input type="text"   v-model="feed" placeholder="Share your thougths....."/>
                    <div>{{feed}}</div>
                    
                </div>
                
            </form>
    
        </div>
    </div> 
</template>
<script>
export default {
   name:"hel", 
   props:["like"],
   
   data(){
       return{
           feed:"",
           about:""
       }
   }
}
</script>
<style scoped>
 h3{
     text-align: center;
 }
 #iron{
     width: 80px;
     height: auto;

 }
 input{
     margin-top: 5px;
     margin-bottom: 10px;
     font-weight: bolder;
     width:50%;
     padding: 6px;
     height: auto;
     background: rgb(210, 189, 238);
     cursor: pointer;
     box-shadow: 10px 10px 5px grey;
     border: 2px solid;
     border-radius: 4px;
     
 }
 input:focus{
     background: lime;
 }
 label{
     font-weight: bold;
 }
 #boss{
     
     width: 40px;
     height:40px,
    
 }
 .box{
     width: 490px;
     height: auto;
     word-wrap: break-word;
     border:2px solid black;
     box-shadow: 10px 10px 5px grey;
     margin: 10px;
     font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
     color: blue;
     background: #b3b1b1;
 }
 @media screen and (max-width: 600px) {
    input{
     
     width:90%;
     
     
 } 
 .box{
     width: 90%;
 }
 }

</style>