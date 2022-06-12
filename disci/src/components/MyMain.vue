<template>
    <div id="bg-container">
        <div id="card-container">
            <MyCard v-for="(item, i) in discsList" :key="i" :discsObject="item" />
        </div>
    </div>
</template>

<script>
    import axios from "axios";
    import MyCard from './MyCard.vue';

    export default {
        name: 'MyMain',
        components: {
            MyCard
        },
        data(){
            return{
                apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
                discsList: []
            }
        },
        created(){
            axios.get(this.apiUrl)
            .then((result) => {
                this.discsList = result.data.response;
            })
        }
    }
</script>

<style lang="scss">

#bg-container{
    background-color: #1E2D3B;
    // height: calc(100vh - 80px);
    #card-container {
        width: 70%;
        margin: 0 auto;
        display: flex;
        justify-content: space-around;
        flex-wrap: wrap;
    }
}

</style>