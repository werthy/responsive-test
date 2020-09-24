<template>
    <div>
        <div class="placeholder">placeholder
            <button @click="test">click</button>
        </div>
        <div class="anchor">
            <div class="div1" :class="divClass" >
            </div>
            <div class="div2">
                <h2 class="text" :class="textClass"> testtest</h2>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        name:"TransimitionTest",
        data() {
            return {
                divClass : "",
                textClass: ""
            }
        },
        methods:{
            test() {
                this.divClass = this.divClass=="" ?  "div1-visible":"";
            },
            // scrollTest(e){
            //     console.log(e);
            // }
        },
        mounted(){
            window.onscroll= () => {
                console.log(window.scrollY);
                if(window.scrollY>530){
                    this.divClass = "div1-visible";
                    this.textClass = "text-visible"
                } else if (window.scrollY<210){
                    this.divClass = "";
                    this.textClass = "";
                }
            }
        }
    }
</script>

<style scoped>
.placeholder {
    height: 200px;
    width: 400px;
    /* text-align: center; */
}
.anchor {
    height: 800px;
    width: 1000px;
    position: relative;
}
.div1 {
    height: 100%;
    width: 30%;
    background-color:blue;
    display: inline-block;
    position: absolute;
    top: 30px;
    left: 0;
    opacity: 0;
    transition: top 2s, opacity 2s ;
}
.div1-visible {
    top: 0;
    opacity: 1;
}
.text {
    opacity: 0;
    top: 30px;
    position: absolute;
    left: 150px;
    transition: top 2s, opacity 2s;
}
.text-visible {
    top: 0;
    opacity: 1;
}
.div2 {
    height: 100%;
    width: 70%;
    background-color:aquamarine;
    display: inline-block;
    position: absolute;
    top: 0;
    left: 300px;

}
</style>