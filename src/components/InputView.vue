<template>
    <div class="form-group">
        <label>{{ label }}</label>
        
        <input type="text" 
            class="form-control" 
            :value="subject"
            @input="onInput"
        >

        <div v-if="err" 
            class="red-text bold-text"
        >
            {{ err }}
        </div>
    </div>
</template>

<script>
import { getCurrentInstance } from 'vue';
export default {
    props: {
        label: {
            type:String,
            required: true,
        },
        err: {
            type:String,
            required: true,
        },
        subject: {
            type:String,
            required: true,
        }
    },

    emits: ['update-subject'],

    setup() {
        const { emit } = getCurrentInstance();
        const onInput = (event) => {
            emit('update:subject',event.target.value);
        }
        return {
            onInput
        }
    }
}
</script>

<style scoped>
    .bold-text {
        font-weight: 900;
    }
    .red-text {
        color: red;
    }
</style>