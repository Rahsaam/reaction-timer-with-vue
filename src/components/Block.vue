<template>
  <div class="block" v-if="showBlocks" @click="stopTimer">
      click me
  </div>
</template>

<script>
export default {
    props: ["delay"],
    data() {
        return{
            showBlocks: false,
            timer: null,
            reactTimer: 0
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlocks = true
            this.startTimer()
            console.log(this.delay);
        }, this.delay)
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactTimer += 10
            }, 10)
        },
        stopTimer() {
            clearInterval(this.timer)
            this.$emit('end', this.reactTimer)
        }
    }
    
}
</script>

<style>

.block{
    width: 400px;
    padding: 100px 0px;
    background-color: #0faf87;
    margin: 40px auto;
    border-radius: 30px;
}

</style>