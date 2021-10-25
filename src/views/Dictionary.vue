<template>
    <input type="text" placeholder="Word for search" v-model="word">
    <button class="btn" @click="search"><img src="../assets/search-interface-symbol.png" style="width:20%">Search</button>
    <br>
    <div class="mt-4" v-if="show">
    <DictResult 
    :showWord="showWord" 
    :phonetics_text="phonetics_text" 
    :phonetics_audio="phonetics_audio" 
    :type="type"
    :origin="origin"
    :definition="definition"
    :example="example"
    />
    </div>
    <div v-else class="mt-4">
        <img src="../assets/drawing.gif" style="width:38%">
        <h3>What word do you want to look up?</h3>
    </div>
</template>
<script>
import DictResult from '../components/DictResult.vue'
export default{
  components: { DictResult },
    name: "Dictionary",
    data(){
        return{
            word:"",
            showWord:null,
            phonetics_text:null,
            phonetics_audio:null,
            type:null,
            definition:null,
            origin:null,
            example:null,
            show:false
        }
    },
    methods:{
        search(){
            fetch(`https://api.dictionaryapi.dev/api/v2/entries/en/${this.word}`)
            .then(response => response.json())
            .then(data => {
                console.log(data)
                this.showWord = data[0]["word"]
                this.phonetics_text = data[0]["phonetic"]
                this.phonetics_audio = data[0]["phonetics"][0]["audio"]
                this.type = data[0]["meanings"][0]["partOfSpeech"]
                this.origin = data[0]["origin"]
                this.definition = data[0]["meanings"][0]["definitions"][0]["definition"]
                this.example = data[0]["meanings"][0]["definitions"][1]["example"]
                })
            this.word = ""
            this.show = true
        }
    }
}
</script>

<style scoped>
    input{
        width:40%;
        padding:10px;
        border-top-right-radius:10px ;
        border-top-left-radius:10px ;
        border-bottom-left-radius:10px ;
        border-bottom-right-radius: 10px;
        border: 1px solid gray;
    }
    button{
        padding: 10px;
        margin-left: 10px;
        background-color: #0096c7;
        color:white;
        border-radius: 10px;
    }
    button:hover{
        color:lightgoldenrodyellow;
    }
</style>