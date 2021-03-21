<template>
    <div class="words">
        <div class="top">
            <div>
                <img @click="speak(data.one)" src="../assets/img/volume.svg" alt="volume" />
                <span>{{ data.one }}</span>
            </div>
            <div>
                <img @click="speak(data.two)" src="../assets/img/volume.svg" alt="volume" />
                <span>{{ data.two }}</span>
            </div>
            <div>
                <img @click="speak(data.three)" src="../assets/img/volume.svg" alt="volume" />
                <span>{{ data.three }}</span>
            </div>
        </div>
        <div class="bottom">
            {{ data.translate }}
        </div>
    </div>
</template>

<script>
export default {
    props: ["data"],
    mounted() {
        // this.speak("How are you?");
    },
    methods: {
        speak(text) {
            //new SpeechSynthesisUtterance object
            let utter = new SpeechSynthesisUtterance();
            utter.lang = "en-UK";
            utter.text = text;
            utter.volume = 1;
            // speak
            window.speechSynthesis.speak(utter);
        },
    },
};
</script>

<style scoped>
.words {
    width: 90%;
    margin: 0 auto;
    margin-top: 20px;
    border-radius: 4px;
    box-shadow: 2px 2px 10px rgba(255, 255, 255, 0.1);
}
.top {
    width: 100%;
    display: flex;
    padding-top: 10px;
    font-size: 18px;
    font-family: "baloo-medium";
}
.top div {
    flex: 1;
    text-align: center;
}
.top img {
    cursor: pointer;
    display: block;
    margin: 0 auto;
}
.top span {
    display: block;
}
.bottom {
    width: 90%;
    margin: 0 auto;
    padding: 8px 0 6px;
    border-top: 1px solid rgba(255, 255, 255, 0.061);
    font-family: "alk";
    font-size: 18px;
}
</style>