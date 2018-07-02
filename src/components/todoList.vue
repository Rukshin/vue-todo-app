<template>
    <div v-if="items.length === 0">
        <p>No hay na' de na'</p>
    </div>
    <div v-else class="todo-list">
        <ul>
            <li v-for="(item, key) in items" :key="key">
                <todoListItem @deleteMe="exterminateChild(key)" :title="item.title" :description="item.description">
                </todoListItem>
            </li>
        </ul>
    </div>
</template>

<script>
    import todoListItem from './todoListItem';
    export default {
        name: 'todoList',
        components: {
            todoListItem
        },
        props: {
            items: Array
        },
        methods: {
            exterminateChild(key) {
                this.$emit('exterminateChild', key);
            }
        }
    }
</script>
