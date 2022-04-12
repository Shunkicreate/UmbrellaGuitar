<template>
    <div class="counter">
        <button type="button" @click="count++">count is: {{ count }}</button>
        <div class="number">
            <h5>175</h5>
        </div>
        <div class="minus button">
            <p><button>－</button></p>
        </div>
        <div class="plus button">
            <p><button>＋</button></p>
        </div>
    </div>

    <div id="disp_count">0</div>
    <input type="button" value="カウントアップ" id="btn_count_up" />
    
    <div class="mode">
        <div class="easy">
            <p><button>簡単</button></p>
        </div>
        <div class="normal">
            <p><button>普通</button></p>
        </div>
        <div class="difficult">
            <p><button>難しい</button></p>
        </div>

    </div>

</template>
<script lang="ts">
import { ref } from 'vue'


const count = ref(0)
</script>


<style>
    .number {
        border: 1px solid;
        width: 10%;
        height: 5%;
    }
    .button {
        width: 10%;
        height: 10%;
        border: 1px solid;
        border-radius: 70px;
    }
</style>