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
    <!-- <children></children> -->
    <checkbox v-model="checked" @change="changeText"></checkbox>
      {{text}}
  </div>
</template>

<script lang="ts">
import { Component, Vue, Provide } from 'vue-property-decorator';
import message from '@/components/message.vue';
import children from '@/components/children.vue';
import checkbox from '@/components/myCheckbox.vue';

@Component({
  components: {
    message,
    children,
    checkbox,
  },
})

export default class Home extends Vue {
  inputMessage: string = '동적데이터 입력';
  count: number = 0;
  checked: boolean = false;
  text: string = '동의하지 않습니다.';

  changeMessage() {
    this.inputMessage = 'change!!';
  }

  counter() {
    this.count++;
  }

  @Provide('message') msg: string = 'provide inject test';

  changeText(checked: boolean) {
    this.checked = checked;
    this.text = this.checked ? '동의합니다.' : '동의하지 않습니다.';
  }
}
</script>
