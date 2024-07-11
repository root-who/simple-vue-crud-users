<template>
  <div>
    <TrashCanIcon v-show="isFormHide" fillColor="#FFFFFF" :size="48" />
    <SquareEditOutline fillColor="#FFFFFF" :size="48" />
    <EyeOutline @click="handle" fillColor="#FFFFFF" :size="48" />
  </div>
</template>

<script setup>
import TrashCanIcon from 'vue-material-design-icons/TrashCan.vue';
import SquareEditOutline from 'vue-material-design-icons/SquareEditOutline.vue';
import EyeOutline from 'vue-material-design-icons/EyeOutline.vue';
import { ref } from 'vue'

const isFormHide = ref(false)

function handle() {
  isFormHide.value = !isFormHide.value
}

</script>

<style scoped>
.container{
  display: inline;
}
.div{
  color:white;
}
</style>
