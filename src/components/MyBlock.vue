<template>
    <div class="block" v-if="showBlock" @click="endTimer">
        {{delay}}
    </div>
</template>

<script>
export default {
    props:['delay'],
    data(){
        return{
            showBlock: false,
            score: 0,
            interval: 0
           
        }
    },
    mounted(){
        setTimeout(()=>{
            this.showBlock=true;
            this.startTimer();
        },this.delay);
    },
    methods:{
         startTimer(){
           this.interval = setInterval(()=>{
                this.score+=50;    
            },50)
        },
        endTimer(){
            clearInterval(this.interval);
            this.$emit('endGame',this.score);
        }
    }
}
</script>

<style>
.block{
        background-color: aqua;
        width: 400px;
        height: 300px;
        margin: 20px auto;
        padding-top: 30px;
}
</style>