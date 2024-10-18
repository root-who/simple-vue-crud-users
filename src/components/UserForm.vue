<template >
    <div class="container">
        <div class="form_controller_container">
            <h2 class="form_title">Usuários</h2>
            <button @click="handleFormState" :class="buttonControllClass">{{ buttonControlName }}</button>
        </div>
        <Transition>
            <form v-if="isFromOpen" class="form_container">
                <div class="input_container">
                    <label class="label">Nome do usuário</label>
                    <input class="input_text" type="text">
                </div>
                <div class="input_container">
                    <label class="label" for="">Função do usuário</label>
                    <input class="input_text" type="text">
                </div>
                <button @click.prevent="handleSaveUser" class="save_user_button">Salvar dados do usuário</button>
            </form>
        </Transition>
    </div>
</template>
<script setup>
import { ref } from "vue"

const isFromOpen = ref(false)
const buttonControlName = ref("Nome do usuário")
const buttonControllClass = ref("new_user_button")


function handleSaveUser(){
    console.log("heelo")
}

function handleFormState(){
    if (isFromOpen.value){
        buttonControlName.value = "Nome do usuário"
        buttonControllClass.value = "new_user_button"
    }else{
        buttonControlName.value = "Cancelar"
        buttonControllClass.value = "cancel_button"
    }
    isFromOpen.value = !isFromOpen.value
}


</script>
<style scoped>

.v-enter-active,
.v-leave-active {
    transition: transform 2s ease;
}

.v-enter-from, .v-leave-to{
    transform: translateY(-120%);
}


.container{
    display: flex;
    flex-direction: column;
    row-gap: 40px;
}
.form_controller_container{
    background-color: white;
    display: flex;
    z-index: 10;
    width: 100%;
    justify-content: space-between;
    align-items: center;
}
.form_title{
    color: black;
    font-size: 50px;
    font-weight: 600;
}
.new_user_button{
    background-color: black;
    color: white;
    border: none;
    border-radius: 5px;
    padding: 18px;
    width: 185px;
}
.cancel_button{
    background-color: #F7F7F7;
    color: black;
    border: none;
    border-radius: 5px;
    padding: 18px;
    width: 185px;
}
.form_container{
    display: flex;
    flex-direction: column;
    row-gap: 20px;
}
.input_container{
    display: flex;
    flex-direction: column;
    row-gap: 5px;
}

.label{
    color: black;
    font-size: 16px;
}

.input_text{
    padding: 16px;
    border: 1px solid #E5E5E5;
    border-radius: 5px;
}
.save_user_button{
    color: white;
    background-color: black;
    border: none;
    padding: 20px;
    width: 100%;
}

</style>