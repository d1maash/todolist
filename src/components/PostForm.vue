<template>
    <div>
        <form @submit.prevent>
            <h4>
                Создание поста
            </h4>
            <my-input v-model="post.title" @input="post.title = $event.target.value" type="text" placeholder="Название" />
            <my-input v-model="post.body" @input="post.body = $event.target.value" type="text" placeholder="Описание" />
            <my-button class="btn" @click="createPost" style="margin-top: 15px;">Создать</my-button>
        </form>
    </div>
</template> 


<script>
export default {
    data() {
        return {
            post: {
                title: '',
                body: '',
            }
        }
    },
    methods: {
        createPost() {
            this.post.id = Date.now();
            this.$emit('create', this.post, 'secon')
            this.post = {
                title: '',
                body: '',
            }
        }
    }

}
</script>

<style>
form {
    display: flex;
    flex-direction: column;

}
</style>