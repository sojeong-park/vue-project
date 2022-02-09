<template>
    <div>
        <p>
            {{alertMessage}}
        </p>
        {{parentMessage}}

        <button @click="counter">children count 증가</button>
    </div>
</template>

<script lang="ts">
    import {Component, Prop, Vue, Watch, Emit} from 'vue-property-decorator'

    @Component
    export default class Children extends Vue {
        @Prop() parentMessage?: string;
        alertMessage: string = '';

        @Watch('parentMessage')
        update(value: string, oldValue: string) {
            this.alertMessage = '메시지가 변경되었습니다.' + value +', '+ oldValue;
        }

        @Emit()
        counter() {
            console.log('pass');
        }
    }
</script>