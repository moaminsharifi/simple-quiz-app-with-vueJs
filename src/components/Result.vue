<template>
    <div class="result">
        <div class="title">{{results[resultIndex].title}}</div>
        <div class="desc">
            {{results[resultIndex].desc}}
        </div>
    </div>
</template>

<script>
    export default {
        name:'Result',
        props:["results", "totalCorrect"],
        computed:{
            resultIndex(){
                let index = 0
                this.results.forEach((element, idx) => {
                    if(element.min <= this.totalCorrect &&
                       this.totalCorrect <= element.max){
                        index = idx
                    }
                });
                return index
            }
        }
    }
</script>

<style>

</style>