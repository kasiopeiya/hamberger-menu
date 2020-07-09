<template>
  <div v-bind:class="{show: isShow}">
    <div id="cover"></div>
    <i class="fa fa-bars" id="hamberger" v-on:click="switchMenu"></i>
    <div id="list">
      <contents v-on:switchMenu="switchMenu"></contents>
    </div>
  </div>
</template>

<script>
import content from "./contents.vue";
export default {
  name: "hambergermenu",
  props: {},
  data: function() {
    return {
      isShow: false
    };
  },
  components: {
    contents: content
  },
  mounted: function() {
    document.getElementById("cover").addEventListener("click", () => {
      this.switchMenu();
    });
  },
  methods: {
    switchMenu: function() {
      this.isShow = !this.isShow;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#cover {
  background: #000;
  opacity: 0.6;
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1;
  display: none;
}

#hamberger {
  float: right;
  cursor: pointer;
  padding: 10px 10px;
  z-index: 3;
  /* color: #fff; */
}

#hamberger::before {
  font-size: 26px;
}
#list {
  z-index: 2;
  position: absolute;
  top: 0;
  right: -280px;
  color: #eee;
  background: #4c81e9;
  padding: 8px;
  box-sizing: border-box;
  width: 280px;
  min-height: 100%;
  transition: 0.4s;
  color: #fff;
}

.show #list {
  right: 0px;
}

.show #cover {
  display: block;
}
</style>
