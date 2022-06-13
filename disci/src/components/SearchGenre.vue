<template>

    <section>
        <label for="genre">Seleziona un genere:</label>

        <select v-model="select" name="genre" id="genre">
            <option @click="valueSelect" value="all">All</option>
            <option @click="valueSelect" value="rock">Rock</option>
            <option @click="valueSelect" value="pop">Pop</option>
            <option @click="valueSelect" value="jazz">Jazz</option>
            <option @click="valueSelect" value="metal">Metal</option>
        </select>
    </section>

</template>

<script>

export default {
    name: 'SearchGenre',
    data() {
        return {
            select: "all"
        }
    },
    methods: {
        valueSelect(){
            this.$emit("mySelect", this.select);
        }
    }
}
</script>

<style lang="scss">
select {
    margin: 20px 10px;
}
</style>