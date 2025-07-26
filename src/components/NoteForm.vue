<template>
    <div class="wrapper">
        <div class="from">
            <p class=title>title</p>
            <button class="close" @click="$emit('onClose')">
                <i class="fa-solid fa-square-xmark"></i>
            </button>
            <input v-model="title">
            >
            <textarea v-model="content" @keydown.enter="$emit('onSave', title, content)">

    </textarea>
            <button class="save" @click="$emit('onSave', title, content)">save</button>
        </div>
    </div>
</template>

<script setup>
import { ref, defineProps, onMounted } from 'vue'
let props = defineProps(['note'])

let title = ref('')
let content = ref('')

onMounted(() => {
        if (props.note?.title) {
            title.value = props.note.title
        }
        if (props.note?.content) {
            content.value=props.note.content
        } 
    })

</script>

<style scoped>
.wrapper {
    width: 100%;
    height: 100%;
    position: fixed;
    background-color: rgba(0, 0, 0, 0.4);
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 10;
}

.from {
    width: 580px;
    height: 600px;
    background: linear-gradient(114.43deg, rgba(255, 255, 255, 0.6) 4%, rgba(255, 255, 255, 0.1) 100%);

    border-radius: 14px;
    border: 1px solid #fff;
    padding: 28px;
    position: relative;



}

input {
    width: 100%;
    height: 40px;
    margin-top: 10px;
    border: none;
    border-radius: 4px;

}

textarea {
    width: 100%;
    height: 280px;
    border: none;
    border-radius: 4px;
    margin-top: 30px;
    resize: none;
}

.save {
    width: 100%;
    height: 40px;
    border-radius: 4px;
    margin-top: 30px;
    background: linear-gradient(128deg, rgba(0, 191, 255, 0.84) 12.75%, rgba(255, 255, 255, 0.67) 83.4%);
    font-size: 24px;
    cursor: pointer;


}

.close {
    background: none;
    border: none;
    font-size: 30px;
    cursor: pointer;
    top: 20px;
    right: 20px;
    position: absolute;
}
</style>