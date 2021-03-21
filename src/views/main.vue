<template>
    <div class="main">
        <div class="cont">
            <input type="text" v-model="word" placeholder="მოძებნა ზმნის პირველი ფორმით" />
            <words v-for="(item, i) in filt" :data="item" :key="i" />
        </div>
    </div>
</template>

<style scoped>
@import url("../assets/fonts/alk/alk.css");
@font-face {
    font-family: "baloo-medium";
    src: url("../assets/fonts/Baloo-Medium.ttf");
}
.main {
    width: 100%;
    min-height: 100vh;
    display: flex;
    justify-content: center;
}
.cont {
    width: 400px;
    padding-bottom: 20px;
    border-radius: 4px;
    box-shadow: 2px 2px 10px rgba(255, 255, 255, 0.198);
}
input {
    display: block;
    margin-top: 10px !important;
    width: 90%;
    height: 30px;
    margin: 0 auto;
    padding-top: 8px;
    padding-left: 4px;
    color: whitesmoke;
    font-size: 18px;
    font-family: "baloo-medium";
    background-color: transparent;
    border: 1px solid whitesmoke;
    border-radius: 4px;
}
input:focus-visible{
    outline: unset;
}
@media (max-width: 450px) {
    .cont {
        width: 100%;
        border-radius: 0;
        box-shadow: none;
    }
}
</style>

<script>
import words from "../components/words";
export default {
    components: {
        words,
    },
    computed: {
        filt() {
            return this.data.filter((el) => {
                if (this.word.trim() == "") return true;
                else {
                    var is_here = el.one.indexOf(this.word.toLowerCase());
                    if (is_here == 0) return true;
                    else return false;
                }
            });
        },
    },
    data() {
        return {
            word: "",
            data: [
                {
                    one: "be",
                    two: "was, were",
                    three: "been",
                    translate: "ყოფნა",
                },
                {
                    one: "beat",
                    two: "beat",
                    three: "beaten",
                    translate: "დარტყმა",
                },
                {
                    one: "become",
                    two: "became",
                    three: "become",
                    translate: "გახდომა",
                },
                {
                    one: "begin",
                    two: "began",
                    three: "begun",
                    translate: "დაწყება",
                },
                {
                    one: "break",
                    two: "broke",
                    three: "broken",
                    translate: "გატეხვა",
                },
                {
                    one: "bring",
                    two: "brought",
                    three: "brought",
                    translate: "მოტანა",
                },
                {
                    one: "build",
                    two: "built",
                    three: "built",
                    translate: "შენება",
                },
                {
                    one: "burn",
                    two: "burnt",
                    three: "burnt",
                    translate: "წვა",
                },
                {
                    one: "buy",
                    two: "bought",
                    three: "bought",
                    translate: "ყიდვა",
                },
                {
                    one: "can",
                    two: "could",
                    three: "-",
                    translate: "შეძლება",
                },
                {
                    one: "catch",
                    two: "caught",
                    three: "caught",
                    translate: "დაჭერა",
                },
                {
                    one: "choose",
                    two: "chose",
                    three: "chosen",
                    translate: "არჩევა",
                },
                {
                    one: "come",
                    two: "came",
                    three: "come",
                    translate: "მოსვლა",
                },
                {
                    one: "cut",
                    two: "cut",
                    three: "cut",
                    translate: "დაჭრა",
                },
                {
                    one: "do",
                    two: "did",
                    three: "done",
                    translate: "კეთება",
                },
                {
                    one: "draw",
                    two: "drew",
                    three: "drawn",
                    translate: "ხაზვა",
                },
                {
                    one: "drink",
                    two: "drank",
                    three: "drunk",
                    translate: "დალევა",
                },
                {
                    one: "drive",
                    two: "drove",
                    three: "driven",
                    translate: "ტარება",
                },
                {
                    one: "eat",
                    two: "ate",
                    three: "eaten",
                    translate: "ჭამა",
                },
                {
                    one: "fall",
                    two: "fell",
                    three: "fallen",
                    translate: "ვარდნა",
                },
                {
                    one: "feel",
                    two: "felt",
                    three: "felt",
                    translate: "შეგრძნება",
                },
                {
                    one: "fight",
                    two: "fought",
                    three: "fought",
                    translate: "ბრძოლა",
                },
                {
                    one: "find",
                    two: "found",
                    three: "found",
                    translate: "პოვნა",
                },
                {
                    one: "fly",
                    two: "flew",
                    three: "flown",
                    translate: "ფრენა",
                },
                {
                    one: "forget",
                    two: "forgot",
                    three: "forgotten",
                    translate: "დავიწყება",
                },
                {
                    one: "get",
                    two: "got",
                    three: "got",
                    translate: "მიღება",
                },
                {
                    one: "give",
                    two: "gave",
                    three: "given",
                    translate: "მიცემა",
                },
                {
                    one: "go",
                    two: "went",
                    three: "gone",
                    translate: "წასვლა",
                },
                {
                    one: "grow",
                    two: "grew",
                    three: "grown",
                    translate: "გაზრდა",
                },
                {
                    one: "hang",
                    two: "hung",
                    three: "hung",
                    translate: "დაკიდება",
                },
                {
                    one: "have",
                    two: "had",
                    three: "had",
                    translate: "ქონა",
                },
                {
                    one: "hear",
                    two: "heard",
                    three: "heard",
                    translate: "სმენა",
                },
                {
                    one: "hide",
                    two: "hid",
                    three: "hidden",
                    translate: "დამალვა",
                },
                {
                    one: "hold",
                    two: "held",
                    three: "held",
                    translate: "დაჭერა",
                },
                {
                    one: "hurt",
                    two: "hurt",
                    three: "hurt",
                    translate: "ტკენა",
                },
                {
                    one: "keep",
                    two: "kept",
                    three: "kept",
                    translate: "შენახვა",
                },
                {
                    one: "know",
                    two: "knew",
                    three: "known",
                    translate: "ცოდნა",
                },
                {
                    one: "learn",
                    two: "learnt",
                    three: "learnt",
                    translate: "სწავლა",
                },
                {
                    one: "leave",
                    two: "left",
                    three: "left",
                    translate: "წასვლა",
                },
                {
                    one: "let",
                    two: "let",
                    three: "let",
                    translate: "ნების დართვა",
                },
                {
                    one: "lie",
                    two: "lay",
                    three: "lain",
                    translate: "წოლა",
                },
                {
                    one: "lose",
                    two: "lost",
                    three: "lost",
                    translate: "დაკარგვა",
                },
                {
                    one: "make",
                    two: "made",
                    three: "made",
                    translate: "კეთება",
                },
                {
                    one: "mean",
                    two: "meant",
                    three: "meant",
                    translate: "მნიშვნელობა",
                },
                {
                    one: "meet",
                    two: "met",
                    three: "met",
                    translate: "შეხვედრა",
                },
                {
                    one: "pay",
                    two: "paid",
                    three: "paid",
                    translate: "გადახდა",
                },
                {
                    one: "put",
                    two: "put",
                    three: "put",
                    translate: "დადება",
                },
                {
                    one: "read",
                    two: "read",
                    three: "read",
                    translate: "წაკითხვა",
                },
                {
                    one: "ride",
                    two: "rode",
                    three: "ridden",
                    translate: "სვლა",
                },
                {
                    one: "ring",
                    two: "rang",
                    three: "rung",
                    translate: "დარეკვა",
                },
                {
                    one: "rise",
                    two: "rose",
                    three: "risen",
                    translate: "ადგომა",
                },
                {
                    one: "run",
                    two: "ran",
                    three: "run",
                    translate: "სირბილი",
                },
                {
                    one: "say",
                    two: "said",
                    three: "said",
                    translate: "თქმა",
                },
                {
                    one: "see",
                    two: "saw",
                    three: "seen",
                    translate: "ხედვა",
                },
                {
                    one: "sell",
                    two: "sold",
                    three: "sold",
                    translate: "გაყიდვა",
                },
                {
                    one: "send",
                    two: "sent",
                    three: "sent",
                    translate: "გაგზავნა",
                },
                {
                    one: "shine",
                    two: "shone",
                    three: "shone",
                    translate: "ნათება",
                },
                {
                    one: "show",
                    two: "showed",
                    three: "shown",
                    translate: "შვენება",
                },
                {
                    one: "shut",
                    two: "shut",
                    three: "shut",
                    translate: "დახურვა",
                },
                {
                    one: "sing",
                    two: "sang",
                    three: "sung",
                    translate: "მღერა",
                },
                {
                    one: "sit",
                    two: "sat",
                    three: "sat",
                    translate: "ჯდომა",
                },
                {
                    one: "sleep",
                    two: "slept",
                    three: "slept",
                    translate: "ძილი",
                },
                {
                    one: "smell",
                    two: "smelt",
                    three: "smelt",
                    translate: "დაყნოსვა",
                },
                {
                    one: "speak",
                    two: "spoke",
                    three: "spoken",
                    translate: "ლაპარაკი",
                },
                {
                    one: "spend",
                    two: "spent",
                    three: "spent",
                    translate: "ხარჯვა",
                },
                {
                    one: "stand",
                    two: "stood",
                    three: "stood",
                    translate: "დგომა",
                },
                {
                    one: "steal",
                    two: "stole",
                    three: "stolen",
                    translate: "მოპარვა",
                },
                {
                    one: "swim",
                    two: "swam",
                    three: "swum",
                    translate: "ცურვა",
                },
                {
                    one: "take",
                    two: "took",
                    three: "taken",
                    translate: "აღება",
                },
                {
                    one: "teach",
                    two: "taught",
                    three: "taught",
                    translate: "სწავლება",
                },
                {
                    one: "tell",
                    two: "told",
                    three: "told",
                    translate: "თქმა",
                },
                {
                    one: "think",
                    two: "thought",
                    three: "thought",
                    translate: "ფიქრი",
                },
                {
                    one: "throw",
                    two: "threw",
                    three: "thrown",
                    translate: "გადაგდება",
                },
                {
                    one: "understand",
                    two: "understood",
                    three: "understood",
                    translate: "გაგება",
                },
                {
                    one: "wake",
                    two: "woke",
                    three: "woken",
                    translate: "გაღვიძება",
                },
                {
                    one: "wear",
                    two: "wore",
                    three: "worn",
                    translate: "ჩაცმა",
                },
                {
                    one: "win",
                    two: "won",
                    three: "won",
                    translate: "მოგება",
                },
                {
                    one: "write",
                    two: "wrote",
                    three: "written",
                    translate: "წერა",
                },
            ],
        };
    },
};
</script>
