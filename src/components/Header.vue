<template>
    <div>
        <nav class="navbar navbar-expand-lg bg-light fixed-top">
            <div class="container-fluid">
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                    data-bs-target="#navbarTogglerDemo01" aria-controls="navbarTogglerDemo01" aria-expanded="false"
                    aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarTogglerDemo01">
                    <a class="navbar-brand" href="#">Rick & Morty</a>
                    <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                        <li class="nav-item">
                            <a class="nav-link active" aria-current="page" href="#">Home</a>
                        </li>
                        <li class="nav-item">
                            <a class="nav-link" :class="colorRed" @click="menu(1)">Personajes</a>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>
    </div>
</template>
<script>
import { useStore } from "vuex";
export default {
    setup() {
        const store = useStore();
    },
    data() {
        return {
            LinkSelected: 0,
        }
    },
    methods: {
        menu(page) {
            this.LinkSelected = page;
            this.$emit('menu', page);
        }
    },
    computed: {
        colorRed() {
            return {
                'espartaco': this.LinkSelected == 1,
            }
        }
    }
};
</script>
<style lang="scss">
.espartaco {
    color: red !important;
}
</style>