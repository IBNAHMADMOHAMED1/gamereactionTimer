<template >
    <div   class="block" v-if="showBlock" @click="stopTime()">
        click me
    </div>

</template>

<script>


export default ({
    
props:['delay'],
data (){
    return{ 
        showBlock: false,
        time : null,
        reactTime:0
    }
},
mounted(){
    // console.log("commp")
    setTimeout(()=>{
      this.showBlock=true;  
      this.statTime()
      console.log(this.delay);
    },this.delay)
},

methods: {
    statTime(){
        this.time=setInterval(()=>{
            {this.reactTime+=10
            // console.log(this.reactTime);
            }

        },10)
    },
    stopTime(){
        clearInterval(this.time)
        // console.log(this.time)
        this.$emit('end',this.reactTime)
    }
}
// updated (){
// console.log('updated')
    
// },
// unmounted (){
//     console.log('unmounted')
// }
    
})
</script>

<style scoped>
.block {
    width: 400px;
    border-radius:10px;
    background-color:#0faf87;
    color: white;
    padding:100px 0;
    margin:40px auto;  
}
</style>
