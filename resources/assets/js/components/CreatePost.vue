<template>
    <form action="" @submit="createPost(post)">
        <h4 class="text-center font-weight-bold">Post creation form</h4>
        <div class="form-group">
            <input type="text" placeholder="Post title" v-model="post.title" class="form-control">

        </div>
        <div class="form-group">
            <textarea v-model="post.content" placeholder="Post content" class="form-control">

            </textarea>
        </div>
        <div class="form-group">
            <button :disabled="!isValid" class="btn btn-block btn-primary" @click.prevent="createPost(post)">Submit
            </button>
        </div>
    </form>
</template>

<script>
    export default {
        name: "CreatePost",
        data() {
            return {
                post: {
                    title: '',
                    content: ''
                }
            }
        },
        mounted() {

        },
        methods: {
            createPost(post) {
                this.$store.dispatch('createPost', post)
            }
        },
        computed: {
            isValid() {
                return this.post.title !== '' && this.post.content !== ''
            }
        }
    }
</script>

<style scoped>

</style>