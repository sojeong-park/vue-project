<template>
    <div class="dropdown">
        <button class="btn btn-secondary dropdown-toggle"
                @click="toggle"
                type="button" id="dropdownMenuButton"
                data-toggle="dropdown"
                aria-haspopup="true"
                aria-expanded="false">
            Dropdown button
        </button>
        <div class="dropdown-menu show" v-show="show" aria-labelledby="dropdownMenuButton">
            <a class="dropdown-item" href="#">Action</a>
            <a class="dropdown-item" href="#">Another action</a>
            <a class="dropdown-item" href="#">Something else here</a>
        </div>
    </div>
</template>

<script lang="ts">
    import {Vue, Component} from 'vue-property-decorator';

    @Component
    export default class Dropdown extends Vue {
        public show: boolean = false;
        public toggle() {
            this.show = !this.show;
        }
    }
</script>

<style>
    .dropdown{
        width: 500px;
    }
</style>