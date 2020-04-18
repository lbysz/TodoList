<template>
    <div :class="['todo-item',todo.completed?'completed':'']">
        <input type="checkbox" v-model="todo.completed">
        <label for="">{{todo.content}}</label>
        <button @click="delItem"></button>
    </div>
</template>

<script>
export default {
    name:'TodoItem',
    props:{
        todo:Object
    },
    methods:{
        delItem(){
            this.$emit('del',this.todo.id)
        }
    }
}
</script>

<style scoped>
.todo-item{
    display: flex;
    justify-content: space-between;
    padding:10px;
    font-size:24px;
    color: #666;
    border-top:1px solid rgba(0,0,0,.1);
}
.todo-item:hover button::after{
    content:'x';
    font-size:24px;
    color:rgb(252,157,154);
}
.completed::after{
    content:'';
    color:#d9d9d9;
    text-decoration: line-through;
}
input{
    width: 50px;
    height: 30px;
    /* appearance: none; */
    text-align: center;
    border: none;
    outline: none;
    display: block;
    border-radius: 50%;
}
label{
    flex: 1; /*让它占据剩余的空间*/
    transition: color 0.4s;
}
button{
    width:40px; 
    background-color:transparent; 
    appearance: none;
    border:none;
    outline: none;
    cursor: pointer;
}
/* input:active{
    color:#d9d9d9;
    text-decoration: line-through;
} */
</style>