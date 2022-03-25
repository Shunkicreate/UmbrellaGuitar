
// yarn devで確認


<template>
    <div>
        <h1>{{ title }}</h1>
        <p>{{ text }}</p>
    </div>
</template>

<script>
export default {
    data(){
        return {
            title: "Header",
            text: "Hello Vue.js!"
        }
    }
}
</script>


// styleタグに併記されているscopedは、「このコンポーネントにのみ、styleを適用しますよ」ということを明示的に宣言しています。
<style scoped>
div{
    border: 1px solid blue
}
h1{
    color: blue
}
p{
    color:blue
}
</style>