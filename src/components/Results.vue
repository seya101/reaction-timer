<template>
    <div>
    <p>Reaction time: {{ showScoreToComponent }} ms</p>
    <h1 :class="txtColor"> {{ rank }}</h1>
    </div>
</template>

<script>
export default {
    props: ['showScoreToComponent' , 'theme'],
    data() {
        return {
            rank: null,
            txtColor: null
        }
    },
    mounted() {
        if (this.showScoreToComponent < 250 ) {
            this.rank = "Awsome! You had a Ninja Fingers"
            this.txtColor = 'txt-green'
            console.log('green')
        }
        else if (this.showScoreToComponent < 400) {
            this.rank = "Rapid Reflexes"
            this.txtColor = 'txt-yellow'
            console.log('yellow')
        }
        else {
            this.rank = "Too Slow! Try Again.."
            this.txtColor = 'txt-red'
            console.log('red')
        }
    }
}
</script>

<style>
.txt-green{
    color: forestgreen;
}
.txt-yellow{
    color:goldenrod;
}
.txt-red{
    color:crimson;
}

</style>