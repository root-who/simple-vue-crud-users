<template >
    <div class="container">
        <div class="user_container">
            <div class="image_container">
                <img class="user_profile" :src="props.user.avatar" alt="">
            </div>
            <div class="info_container">
                <span class="user_id">#{{props.user.id}}</span> 
                <span class="user_name">{{ props.user.first_name + " " + props.user.last_name}}</span>
               <span class="user_email">{{props.user.email}}</span>
            </div>
        </div>
        <div class="actions_container">
            <TrashCanIcon @click="delete_user" fillColor="#797979" :size="20" />
            <SquareEditOutline @click="edit_user" fillColor="#797979" :size="20" />
            <EyeOutline @click="view_user" fillColor="#797979" :size="20" />
        </div>
    </div>
</template>
<script setup>

const props = defineProps({
  user: Object
})


function delete_user(){}
function edit_user(){}
function view_user(){}


import TrashCanIcon from 'vue-material-design-icons/TrashCan.vue';
import SquareEditOutline from 'vue-material-design-icons/SquareEditOutline.vue';
import EyeOutline from 'vue-material-design-icons/EyeOutline.vue';

</script>
<style scoped>

.container{
    flex: 1;
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: calc(100% - 40px);
    padding: 20px;
    background-color: #F7F7F7;
    color: #797979;
}
.user_id{
    font-size: 16px;
}
.user_name{
    font-size: 18px;
    color: black;
    font-weight: 600;
}
.user_email{
    font-size: 16px;
}
.user_container{
    display: flex;
    align-items: center;
    row-gap: 20px;
    column-gap: 30px;
}

.image_container{
    display: flex;
    justify-items: center;
    width: 80px;
    height: 80px;
    background-color: red;
    border-radius: 10px;
}

.user_profile{
    object-fit: cover;
    width: 100%;
    height: 100%;
    border-radius: 10px;
    
}

.info_container{
    display: flex;
    flex-direction: column;
}

.actions_container{
    display: flex;
}

</style>