<template>
  <p>Reaction time = {{score}} ms</p>
  <h1 class="rank">{{this.rank}}</h1>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return{
            rank: null
        }
    },
    mounted() {
        if (this.score < 200){
            this.rank = "Ninja Fingers"
        } else if (this.score < 400){
            this.rank = "Rapid Reflexes"
        } else {
            this.rank = "Snail Pace..."
        }
        console.log(this.score);
    }
}
</script>

<style>
    .rank{
        color: #0faf87;
    }
    p{
        margin-top: 30px;
    }

</style>