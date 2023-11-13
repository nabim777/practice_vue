// inside here we write html
<template>
    <h1>Hello World from Nepal</h1>
    <h2>{{name}}</h2>
    <h3>{{msg}}</h3>
</template>
<script>
export default {
  name: "HomeSection",
  props: {
    name: String,
    msg: String,
  },
};
</script>
