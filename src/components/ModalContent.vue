<!--
 * @Author: hhhhhq
 * @Date: 2021-07-02 12:16:05
 * @LastEditors: hhhhhq
 * @LastEditTime: 2021-07-02 12:49:20
 * @Description: file content
-->
<template>
  <div>
    <h2>{{ title }}</h2>
    <p>{{ msg }}</p>
    <button @click="$emit('close')">Close</button>
  </div>
</template>

<script setup>
import { defineProps } from "vue"

emits: ["close"]

defineProps({
  title: String,
  msg: String,
})
</script>

<style scoped></style>
