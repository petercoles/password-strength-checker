<template>

    <div class="password-strength-checker">

        <input
            type="password"
            v-model="password"
            :name="name"
            :class="class"
            :placeholder="placeholder"
            @keyup="check"
        >

        <div :class="status" :style="{width: strength + '%'}"></div>

    </div>

</template>

<script>

    export default {
        props: ['name', 'password', 'class', 'placeholder'],

        data: function() {
            return {
                score: 0,
            }
        },

        computed: {
            strength: function() {
                return this.score * 25;
            },

            status: function() {
                return 'strength-bar ' + ['', ' poor', ' weak', ' acceptable', ' good'][this.score];
            }
        },

        methods: {
            check: function() {
                var result = zxcvbn(this.password);
                this.score = result.score;
            }
        },

        events: {
            reset: function() {
                this.score = null;
                this.password = '';
            }
        }
    }

</script>

<style>
    .strength-bar {
        height: 4px; margin-top: -2px; }
    .strength-bar.poor {
        background-color: #d9534f; }
    .strength-bar.weak {
        background-color: #f0ad4e; }
    .strength-bar.acceptable {
        background-color: #5bc0de; }
    .strength-bar.good {
        background-color: #5cb85c; }
</style>
