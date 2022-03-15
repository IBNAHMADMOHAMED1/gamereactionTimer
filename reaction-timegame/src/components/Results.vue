<template>
<div>
       <p>score  dyalk : {{score}} ms</p>
        <p> {{rank}}</p>
</div>
  
</template>

<script>


export default ({
    props:['score'],
    data () {
        return { 
            rank:null,
        }
    },
    mounted(){
        console.log(this.score)
        if (this.score<25000){
            this.rank =' Good '
        } else if (this.score<400){
            this.rank ='Nice'

        }else if (this.score>100){
            this.rank ='Woow'
        }
        console.log(this.rank)
    }
    
    })
</script>
