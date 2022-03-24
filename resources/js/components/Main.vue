<template>
    <div>
        <h1>Titoli POST</h1>
        <ol>
            <li v-for="(post, index) in posts" :key="index">
                <h1>Titolo</h1>{{post.title}}
                <h1>Contenuto</h1>{{post.content}}
                <h1>Data Post</h1>{{post.post_date}}
                <h1>Autore</h1>{{post.author}}
                <h1>Slug</h1>{{post.slug}}
                <h1>Categoria</h1>{{post.category_id}}
                <h1>Tags</h1>{{post.tags}}
            </li>
        </ol>
    </div>
</template>


<script>

export default ({
    name : "Main",
    data(){
        return{
            posts:[
                // "titolo1",
                // "titolo2",
                // "titolo3"
            ]
        }
    },
    created(){
        axios
        .get("/api/posts")
        .then( apirisp =>{
            this.posts = apirisp.data;
            console.log(apirisp)
        })
    }
})
</script>

<style scoped>

</style>

