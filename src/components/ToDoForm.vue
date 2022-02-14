<template>
    <form>
        <label class="label__lg" for="new-todo-input">
            What needs to be done?
        </label>
        <input class="input__lg" type="text" v-model.lazy.trim="label" id="new-todo-input" autocomplete="off" name="new-todo">
        <button class="btn btn__primary btn__lg" @click.prevent="onSubmit" type="submit">
            Add
        </button>
    </form>
</template>

<script>
export default {
    methods: {
        onSubmit(){
            if(this.label === ''){
                return
            }
            // passing the data to the parent i.e. app.vue by emmiting an event
            this.$emit("todo-added", this.label);
            this.label = '';
        }
    },
    data(){
        return{
            label: ''
        }
    }
}
</script>