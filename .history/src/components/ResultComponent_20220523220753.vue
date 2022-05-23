<template>
    <div class="result">
        <div class="title">You got sample result {{ results[resultIndex] }}!</div>
        <div class="desc">
            Enter a short description here about the result.
        </div>
    </div>
</template>

<script>
export default {
    props: ['results', 'totalCorrect'],
    computed:{
        resultIndex(){
            let index = 0;
            this.results.forEach((e, i) => {
                if(e.min <= this.totalCorrect && e.max >= this.totalCorrect){
                    index = i;
                }
            });
            return index
        }
    }
}
</script>