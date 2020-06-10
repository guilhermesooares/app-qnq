<template>
  <button @click="$emit('click')" class="btn btn-1">
    <slot></slot>
  </button>
</template>

<script>
export default {
}
</script>

<style>
.btn {
  background: none;
  cursor: pointer;
  padding: 0.7rem 2rem;
  display: inline-block;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-weight: 700;
  outline: none;
  position: relative;
  transition: all 0.3s;
}
.btn-1 {
  border: 3px solid #fff;
  color: #fff;
}
.btn-1:hover,
.btn-1:active {
  color: black;
  background: #fff;
}
</style>