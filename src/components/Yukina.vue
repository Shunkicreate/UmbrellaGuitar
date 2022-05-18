<template>
    <div class="set">
        <div class="counter">
            <div class ="kazu">{{ count }}</div>
            <button class="minus bt" type="button" @click="Minus()"><img src="../assets/Subtract.svg"></button>
            <button class="plus bt" type="button" @click="computed()"><img src="../assets/Group 5.svg"></button>
        </div>

        <div class="poti">
            <div class="strk sum">
                <p>stroke</p>
                <button class="stroke mode" type="button" @click="Change_stroke_level()">{{ stroke_level }}</button>
            </div>

            <div class="code sum">
                <p>code</p>
                <button class="code mode" type="button" @click="Change_code_level()">{{ code_level }}</button>
            </div>
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
        function computed() {
            count.value = count.value + 1
        }

        function Minus() {
            count.value = count.value - 1
        }

        var array = ref(['easy', 'difficult'])
        let i = 0

        let stroke_level = ref(array.value[i])
        let code_level = ref(array.value[i])

        function Change_stroke_level() {
            if (i < 1){
                i = i + 1
            }else{
                i = 0
            }
            stroke_level.value = array.value[i]
        }

        function Change_code_level() {
            if (i < 1){
                i = i + 1
            }else{
                i = 0
            }
            code_level.value = array.value[i]
        }

        return {
            count,
            Change_stroke_level,
            Change_code_level,
            stroke_level,
            code_level,
            plusOne,
            computed,
            Minus
        }
    }
});


</script>


<style>
    .set {
        background-color: #E9E9E8;
        padding-top: 3%;
        padding-bottom: 2%;
        width: 30%;
    }

    .counter {
        box-shadow: -2px -2px 3px #a5aaabe5;
        padding-top: 6%;
        margin: 3% 10%; 
    }

    .kazu {
        box-shadow: 2px 2px 3px #a5aaabe5;
        padding: 2% 3%;
        margin: 5% 20%;
        margin-top: 1%;
        font-family: 'Nunito Sans';
    }

    .bt {
        margin: 0% 5%;
        border: none;
        background-color: #E9E9E8;
    }

    .poti {
        box-shadow: -2px -2px 3px #a5aaabe5;
        margin: 8% 10%; 
    }

    /* .strk {
        margin-top: 20%;
        margin-bottom: 5%;
    }

    .code {
        margin-top: 0%;
        margin-bottom: 5%;
    } */

    .mode {
        background-color: #E9E9E8;
        margin-bottom: 3%;
    } 

    .sum {
        font-family: 'Nunito Sans';
    }

</style>