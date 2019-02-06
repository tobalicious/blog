<template>
  <div
    class="level is-marginless selector"
    @click="test"

  >
    <b><slot></slot></b>
  </div>
</template>

<script>
export default {
  name: "SelectorCard",
  props: {
    text: String,
    index: Number
  },
  methods: {
    test() {
      this.$emit('option-selected');
    }
  }
}
</script>

<style lang="css" scoped>
.selector {
  font-size: 1.5em;
  color: black;
  padding: 5px;
  width: 100%;
  cursor: pointer;
}

.selector:hover {
  background-color: #BF9AFF;
  color: white;

}

</style>
