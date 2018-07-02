<template>
    <div class="content" :class="isError">
        <input type="text" v-model="title" @keyup.enter="changeFocus">
        <input type="text" v-model="description" ref="description" @keyup.enter="submitTodo">
    </div>
</template>

<script>
    export default {
        name: 'inputForm',
        data() {
            return {
                title: '',
                description: '',
                error: false
            }
        },
        computed: {
            isError() {
                return {'error': this.error};
            }
        },
        watch: {
            title() {
                this.error = false;
            },
            description() {
                this.error = false;
            }
        },
        methods: {
            changeFocus() {
                return this.$refs.description.focus()
            },
            submitTodo() {
                if (!(this.title !== '' && this.description !== '')) {
                    this.error = true;
                } else {
                    this.$emit('todoWasSubmited', {
                        title: this.title,
                        description: this.description
                    });
                    this.title = '';
                    this.description = '';
                }
            }
        }
    }
</script>

<style>
    .content {
        background: green;
    }
    .content.error {
        background: red;
    }
</style>
