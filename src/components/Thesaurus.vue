<template>
    <div>
        This is the program
        <label for="userWord">Give a word:</label>
        <input v-model="userWord" type="text" name="userWord">
        <button @click="loadData()">Get ...</button>
        <div>{{ userWord }}</div>
        <div>
            <p v-show="this.response" v-for="word in this.wordType" :key="{ word }">
                {{ word }}
            </p>
        </div>
    </div>
</template>

<script>
import axios from "axios";
    export default{
        name: "ThesaurusDiv",
        data(){
            return{
                userWord: "",
                response: "",
                wordType: {},
                syn: [],
                url: ""
            }
        },
        methods:{
            async loadData(){ 
                this.url = "https://words.bighugelabs.com/api/2/f7756b55df551f7e7e374ee41e97bb5a/"+ this.userWord +"/json";
                try{
                    this.response = await axios.get(this.url);
                    console.log(this.response);
                    this.wordType = Object.values(this.response["data"]["noun"]["syn"]);
                    console.log(this.wordType);
                }catch(e){
                    alert("Error: "+e.response.status+"\nMessage: "+e.response.data.error.message);
                }
            },
        }
    }
</script>