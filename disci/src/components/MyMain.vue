<template>
    <main id="bg-container">

        <SearchGenre @mySelect="changeGenre"/>

        <section id="card-container">
            <MyCard v-for="(item, i) in discsList" :key="i" :discsObject="item" />
        </section>
    </main>
</template>

<script>
import axios from "axios";
import MyCard from './MyCard.vue';
import SearchGenre from './SearchGenre.vue';

export default {
    name: 'MyMain',
    components: {
        MyCard,
        SearchGenre

    },
    data() {
        return {
            apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            discsList: [],
            selectGenre: "all",

        }
    },
    created() {
        axios.get(this.apiUrl)
            .then((result) => {
                this.discsList = result.data.response;
            })
    },
    methods: {
        changeSelect(){
            this.selectGenre = "all"
        }
    },
    computed: {
        filteredGenre(){
            if(this.selectGenre === "all"){
                return this.discsList;
            } else {
                return this.discsList.filter(item => {
                    return item.genre.toLowerCase().includes(this.selectGenre.toLowerCase())
                })
            }
        }
    }
}
</script>

<style lang="scss">
#bg-container {
    background-color: #1E2D3B;
    text-align: center;
    color: white;
    
    select{
        margin: 20px 10px;
    }

    #card-container {
        width: 70%;
        margin: 0 auto;
        display: flex;
        justify-content: space-around;
        flex-wrap: wrap;
    }
}
</style>