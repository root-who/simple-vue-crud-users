<template >
    <ul class="user_list_container">
        <li class="user_item_container" v-for="user in userList" :key="user.id">
            <UserCard :user="user"/>
        </li>
    </ul>
</template>
<script setup>
import axios from 'axios';
import { reactive, toRefs, computed, onMounted, ref } from "vue";
import UserCard from './UserCard.vue';
let id = 0
const users = ref()
const userList = ref(
    [
        { 
            id: id++, 
            name: 'João Paulo',
            email: "joaopaulo_gonzaga@outlook.com",
            position: "SWE III"
        },
        { 
            id: id++, 
            name: 'João Paulo',
            email: "joaopaulo_gonzaga@outlook.com",
            position: "SWE III"
        },
        { 
            id: id++, 
            name: 'João Paulo',
            email: "joaopaulo_gonzaga@outlook.com",
            position: "SWE III"
        },
        { 
            id: id++, 
            name: 'João Paulo',
            email: "joaopaulo_gonzaga@outlook.com",
            position: "SWE III"
        },
        { 
            id: id++, 
            name: 'João Paulo',
            email: "joaopaulo_gonzaga@outlook.com",
            position: "SWE III"
        },
    ]
)

const fetchUsers = () => {
    axios.get('https://reqres.in/api/users')
    .then(response => {
        users.value = response.data
    })
}

onMounted(() => {
    fetchUsers()
})
console.log(users)

</script>
<style scoped>
.user_list_container{
    list-style: none;
    display: flex;
    flex-direction: column;
    row-gap: 20px;
    flex: 1;
    padding: 0;
}
.user_item_container{
    flex: 1;
    display: flex;
}
</style>