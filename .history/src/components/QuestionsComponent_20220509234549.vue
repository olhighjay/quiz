<template>
    <div class="questions-ctr">
        <div class="progress">
            <div class="bar"></div>
            <div class="status">1 out of 3 questions answered</div>
        </div>
        <div class="single-question" v-for="(question, qi) in questions" :key="question.q" v-show="questionsAnswered === qi">
            <div class="question">{{ question.q }}</div>
            <div class="answers">
                <div class="answer" v-for="answer in question.answers" :key="answer.text" @click.prevent="selectAnswer(answer)">{{ answer.text }}</div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props:['questions', 'questionsAnswered']
}
</script>