<template>
    <div class="container">
        <div class="left">
            <h1>{{showWord}}</h1>
            <button class="btn audio" @click="playaudio"><img src="../assets/audio.png" ></button>
            <em>/{{phonetics_text}}/</em>
            <br>
           <h3><b>{{type}}</b></h3>
           <p><span style="color:green">Origin:</span> {{origin}}</p>
           <br>
           <p><span style="color:green">Definition:</span> {{definition}}</p>
           <br>
           <p v-if="example !==null"><span style="color:green">Example:</span> {{example}}</p>

        </div>
    </div>
</template>

<script>
 export default{
     name:"DictResult",
     props:[
         "showWord","phonetics_text","phonetics_audio","type","definition","origin","example"
     ],
     methods:{
         playaudio(){
             console.log(this.phonetics_audio)
             let audio = new Audio(this.phonetics_audio) 
             audio.play()
         }
     }
 }
</script>

<style scoped>
    .audio{
        border-radius: 50%;
        background-color: gainsboro;
        padding: 10px;
    }
    .left{
        padding: 20px;
        background-color: gainsboro;
        border-radius: 10px;
        height: 50%;
        justify-content: left;
    }
    p{
        font-size: 20px;
    }
    h1{
        text-decoration: underline;
    }
</style>