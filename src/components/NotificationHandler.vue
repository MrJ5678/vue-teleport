<!--
 * @Author: hhhhhq
 * @Date: 2021-07-02 11:36:41
 * @LastEditors: hhhhhq
 * @LastEditTime: 2021-07-02 12:22:34
 * @Description: file content
-->
<template>
  <div class="root">
    <button @click="isOpen = true">Open</button>
    <teleport to="body">
      <transition name="fade">
        <div v-if="isOpen" class="modal" @click="isOpen = false">
          <div>
            <!-- <h2>Notification</h2>
            <p>Some filler text</p>
            <button @click="isOpen = false">Close</button> -->
            <ModalContent
              @close="isOpen = false"
              title="Notification"
              msg="Some filler text"
            />
          </div>
        </div>
      </transition>
    </teleport>
  </div>
</template>

<script setup>
import { ref } from "vue"
import ModalContent from "./ModalContent.vue"

const isOpen = ref(false)
</script>

<style>
.root {
  position: relative;
}

.modal {
  position: absolute;
  top: 0;
  left: 0;
  background-color: rgba(0, 0, 0, 0.7);
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal > div {
  background-color: #fff;
  padding: 50px;
  border-radius: 10px;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
