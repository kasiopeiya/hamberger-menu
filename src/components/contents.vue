<template>
  <ul id="menu">
    <div id="close" v-on:click="$emit('switchMenu')">×</div>
    <li>
      <a href="#">home</a>
    </li>
    <li>
      <a href="#">menu</a>
    </li>
    <li>
      <a href="#">otter</a>
    </li>
    <li>
      <a href="#">contact</a>
    </li>
  </ul>
</template>

<script>
export default {
  name: "contents",
  props: []
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#close {
  text-align: right;
  font-size: 26px;
  cursor: pointer;
}
#menu li {
  list-style: none;
  margin-bottom: 28px;
}

#menu li:hover {
  text-decoration: underline;
  opacity: 0.4;
}

#menu li a {
  text-decoration: none;
  font-size: 20px;
  /* color: #fff; */
}
</style>
