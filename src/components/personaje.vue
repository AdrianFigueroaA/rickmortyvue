<template>
<div>
  <img :src="src" alt />
  <h3 >{{name}}</h3>
</div>
</template>





<script>
export default {
  name: "Personaje",
  props: {
    src: String,
    name: String,
    
  },
  methods: {
    
  },
};
</script>