<template>
  <div class="hello" :class='outdivtype'>
    <div class = "div1" :class='div1type'>

    </div>
    <div class = "div2" :class='div2type'>

    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      outdivtype: 'large',
      div1type: 'large1',
      div2type: 'large2'
    }
  },
  computed: {
    div1width(){
      return (this.width-400)*0.3
    }
  },
  props: {
    msg: String,
    width: Number,
    height: Number
  },
  watch:{
    width(){
      if(this.div1width>300)
        {
          this.div1type = 'large1';
          this.div2type = 'large2';
          this.outdivtype = 'large';
        }
      else
      {
        this.div1type = 'middle1';
        this.div2type = 'middle2';
        this.outdivtype = 'middle';
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>
.hello 
  min-width: 950px
  min-height: 700px
  // margin: 0 200px;

.div1
  background-color : black 
  display: inline-block;
  height: 100%

.div2
  background-color : blue
  display: inline-block;
  height: 100%

.large
  margin: 0 200px

.large1
  width: 30%

.large2
  width: 70%
  // margin-right: 200px

.middle
  margin: 0

.middle1
  width: 250px

.middle2
  margin: 0 100px
  width: 50%

</style>
