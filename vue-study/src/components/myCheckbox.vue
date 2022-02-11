<template>
    <input type="checkbox" :checked="checked" @change="change">
</template>

<script lang="ts">
    import { Component, Model, Vue, Emit } from 'vue-property-decorator';

    @Component
    export default class MyCheckbox extends Vue{
        @Model('change', {type: Boolean}) readonly checked!: boolean;

        @Emit()
        change(event: { target: HTMLInputElement }) {
            return event.target.checked;
        }
    }

</script>
