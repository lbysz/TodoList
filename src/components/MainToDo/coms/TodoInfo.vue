<template>
    <div class="todo-info">
        <span class="total">{{total}} item left</span>
        <div class="tab">
            <a :class="[state==item?'active':'']" v-for="(item,index) in states" :key="index" @click="toggleState(item)">{{item}}</a>
        </div>
        <button class="clear" @click="clearCompleted">Clear Completed</button>
    </div>
</template>

<script>
export default {
    name:'TodoInfo',
    props:{
        total:Number
    },
    data(){
        return{
            states:['all','active','completed'],
            state:'all'
        }
    },
    methods:{
        toggleState(state){
            this.state=state
            this.$emit('toggleState',state)
        },
        clearCompleted(){
            this.$emit('clearCompleted')
        }
    }
}
</script>

<style scoped>
.todo-info{
    display: flex;
    justify-content: space-between;
    padding:5px 10px;
    font-weight: 400;
    line-height:30px;
    border-top:1px solid rgb(131,175,155);
}
.total{
    color:rgb(254,67,101);
}
.tabs{
    display: flex;
    justify-content: space-between;
    width:200px;
}
a{
    padding: 0 10px;
    border:1px solid rgb(252,157,154);
    border-radius:5px;
    margin:5px;
}
a:active{
    background-color: rgb(252,157,154);
    color:#fff;
    cursor: pointer;
}
.clear{
    padding:0 10px;
    background-color: rgb(131,175,155);
    border-radius:5px;
    color:#fff;
    appearance: none;
    border:none;
    outline: none;
}
</style>