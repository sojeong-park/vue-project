<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <message></message>
    <children :parentMessage="inputMessage"></children>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
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
}
</script>
