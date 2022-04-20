<template>
    <div class="set">
        <div class="counter">
            <div class ="kazu">{{ count }}</div>
            <button class="minus bt" type="button" @click="Minus()">－</button>
            <button class="plus bt" type="button" @click="computed()">＋</button>
        </div>

        <div>
            <h5 class="strk">ストローク</h5>
            <button class="stroke mode" type="button" @click="Change()">{{ change }}</button>
        </div>

        <div>
            <h5 class="code">コード</h5>
            <button class="stroke mode" type="button" @click="Change()">{{ change }}</button>
        </div>
    </div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue';
export default defineComponent({
    name: "Yukina",

    setup() {
        const count = ref(175)
        const plusOne = computed
        const minusOne = Minus

        function computed() {
            count.value = count.value + 1
        }

        function Minus() {
            count.value = count.value - 1
        }

        var array = ['やさしい', 'ふつう', 'むずかしい']
        let i = 0

        const change = array[i]
        const modechange = Change

        function Change() {
            if (i < 2){
                i = i + 1
            }else{
                i = 0
            }        
        }

        
        console.log(change);

        

        return {
            count,
            change,
            Change,
            plusOne,
            computed,
            Minus
        }

        // plusOne.value++ // error
    }
});


</script>


<style>
    .set {
        border: 1px solid;
        margin-top: 3%;
        margin-left: 5%;
        margin-right: 70%; 
    }
    .kazu {
        border: 2px solid;
        padding: 2% 3%;
        margin: 5% 30%;
        margin-top: 15%;
    }

    .bt {
        margin: 0% 5%;
        border-radius: 100%; 
        font-size: 100%;
        border: none;
        background-color: rgb(237, 173, 110);
        border-color: rgba(204, 172, 132, 0.727);
        
    }
    .strk {
        margin-top: 20%;
        margin-bottom: 5%;
    }
    .code {
        margin-top: 0%;
        margin-bottom: 5%;
    }
    .stroke.mode {
        margin-bottom: 15%;
        background-color: rgb(237, 173, 110);
        border-color: rgba(204, 172, 132, 0.727);
        /* font-weight: 10; */
        color: rgb(77, 75, 75)
    }
</style>