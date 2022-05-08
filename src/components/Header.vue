<template>
  <header>
    <h2>{{wordValue ? wordValue:'Word Hunt'}}</h2>
    <div class="input-wrap">
      <input
        type="text"
        placeholder="Search a Word"
        v-model="wordValue"
        @input="$emit('update:modelValue', $event.target.value)"
      />
    </div>
  </header>
</template>

<script setup>
import { ref } from "vue";
const wordValue = ref('');
defineEmits(["update:modelValue"]);
</script>

<style lang="scss" scoped>
header {
  height: 30vh;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
  h2 {
    font-size: 7vw;
    font-weight: 100;
    @media (max-width: 1000px) {
      font-size: 11vw;
    }
  }
  .input-wrap {
    input {
      width: 50vw;
      border: none;
      background-color: #282c34;
      border-bottom: 1px solid rgba(197, 188, 188);
      padding: 5px;
      font-size: 18px;
      color: white;
      &:focus {
        outline: none;
        border-bottom: 1px solid white;
      }
      &::placeholder {
        color: rgba($color: white, $alpha: 0.6);
      }
    }
  }
}
</style>
