<template>
    <span>
        {{ title }} - {{ description }}
        <button @click="deleteItem">X</button>
    </span>
</template>

<script>
    export default {
        name: 'todoListItem',
        props: {
            title: String,
            description: String,
        },
        methods: {
            deleteItem() {
                this.$emit('deleteMe');
            }
        }
    }
</script>
