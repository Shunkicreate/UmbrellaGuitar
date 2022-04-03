<template>
    <div class="counter">
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