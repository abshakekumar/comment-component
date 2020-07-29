<template>
    <section class="todo-list-container">
        <input 
        v-model="inputVal"
        @keyup.enter="hanleEnterClick"
        type="text" />
        <div v-for="item in list" :key="item.id">
            {{item.value}}
        </div>
        Entered Val: {{inputVal}}
    </section>
</template>

<script>
export default {
    name: 'TodoList',
    props: ['list'],
    data() {
        return {
            inputVal: 'default'
        }
    },
    methods:  {
            hanleEnterClick: function () {
                console.log('Handle Keypress');
                this.$emit('add-todo', this.inputVal);
                this.$nextTick(()=>{
                    this.inputVal = ""
                })
            }
    }
}
</script>

<style scoped>
.todo-list-container {
    padding: 20px;
}
</style>