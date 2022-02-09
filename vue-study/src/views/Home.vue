<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <message></message>
    <!-- <children :parentMessage="inputMessage"></children>
    <button @click="changeMessage">메시지를 바꿔주자</button> -->
    <!-- <children @counter="counter"></children>
    <div>
      부모에서 숫자를 보여준다 {{count}}
    </div> -->
    <children></children>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Provide } from 'vue-property-decorator';
import message from '@/components/message.vue';
import children from '@/components/children.vue';

@Component({
  components: {
    message,
    children,
  },
})
export default class Home extends Vue {
  inputMessage: string = '동적데이터 입력';
  count: number = 0;
  
  changeMessage() {
    this.inputMessage = 'change!!';
  }

  counter() {
    this.count++;
  }

  @Provide('message') msg: string = 'provide inject test';
}
</script>
