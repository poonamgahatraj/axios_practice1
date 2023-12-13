<template>
    <div class="container">
        <div class="header">
            <ul style="list-style-type: none; display: flex; justify-content: center;align-items: center;">
                <li>Home </li>
                <li>User Photos</li>
                <li>Documentation</li>
                <li>Change Log</li>
                <li>Satas & Graphs</li>
                <li>Donate</li>
                <li>Copyright Notice</li>
                <li>Photoshop Extension</li>

            </ul>
        </div>
        <div class="content">
            <div style="display:flex;justify-content: center;">
                <P style="font-size: 40px;">RANDOM USER GENERATOR</P>
            </div>
            <div  style="display:flex;justify-content: center;font-size: 20px;">
                <P >A free, open-source API for generating random user data. Like Lorem Ipsum, but for people.</P>
            </div>
            <div  style="display:flex;justify-content: center;">
                
                <P >Follow us @randomapi</P>
            </div>
        </div>

        <div class="main-content">
            <div style="border:1px solid#999999;width:108px;border-radius:50%;margin:auto; margin-top: 5%;">
            <div   v-for="item in  api_data.results" style="border:3px solid white;height:100px;width:100px;border-radius:50%;margin:auto;" >
                <div>
                     <img :src="item.picture.large" style="border-radius: 50%;
    width: 100%;">
                </div>
            </div>
        </div>
            <div >
                <p style="display: flex;
    justify-content: center;font-size: 20px;color:#999999">Hi, My name is</p>
    <div v-for="item in  api_data.results " style="display:flex; justify-content: center;font-size: 20px;color:black;">
    <p style="margin-right: 15px;"><b>{{ item.name.first }}</b></p>
    <p><b>{{ item.name.last }}</b></p>

    
    </div>
    <div v-for="item in  api_data.results " >
        <p style="display: flex;
    justify-content: center;font-size: 20px;color:#999999">My email address is</p>
    <p style="display:flex; justify-content: center;font-size: 20px;color:black;">{{ item.email }}</p>
    </div>

    <div v-for="item in  api_data.results " >
        <p style="display: flex;
    justify-content: center;font-size: 20px;color:#999999">My birthday is</p>
    <p style="display:flex; justify-content: center;font-size: 20px;color:black;">{{ item.dob.date }}</p>
    </div>

    <div v-for="item in  api_data.results " >
        <p style="display: flex;
    justify-content: center;font-size: 20px;color:#999999">My address is</p>
    <div style="display:flex;justify-content: center;font-size: 20px;">
        <p style="display:flex; justify-content: center;font-size: 20px;color:black;margin-right:10px;">{{ item.location.street.number }}</p>
         <p style="display:flex; justify-content: center;font-size: 20px;color:black;">{{ item.location.street.name }}</p>
    </div>
    
    </div>


   
            </div >

            
        </div>
    </div>
</template>


<script>
import axios from 'axios';
export default{
    data(){
        return{
            
            api_data:{},
   
    "info": {
        "seed": "83a946a9cbec449e",
        "results": 1,
        "page": 1,
        "version": "1.4"
    }
}
        },


    mounted () {
    axios
      .get('https://randomuser.me/api/?nat=us&randomapi')
      .then(response =>{
        this.api_data=response.data
      } )
  }

}





</script>

<style>

.container{
    position:relative;
}
.header{
    display:flex;
    justify-content: center;
    background:black;
    color:white;
    font-size:20px;
}

li{
    margin-right:20px;
}

.content{
    background:#2C2E31;
    COLOR:WHITE;
   
    flex-direction: column;
    justify-content: center;

height:500px;
}

.main-content{
    background:#F9F9F9;
    width:60%;
    height:70%;
   margin:auto;
   
    position:absolute;
    left: 21%;
    top: 61%;
}
</style>