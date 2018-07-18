<template>
  <div class="first">
     <p>First block</p>
     <button @click="hdlClick">Switch</button>
  </div>
</template>

<script>
export default {
  name: "First",
  props: [],
  data(){
    return{
       nameElement: "Second"
    }
  }
  ,
  methods: {
    hdlClick() {
      this.$emit("click", this.nameElement);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.first {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  width: 50%;
  margin: 0 auto;
  height: 400px;
}
</style>
