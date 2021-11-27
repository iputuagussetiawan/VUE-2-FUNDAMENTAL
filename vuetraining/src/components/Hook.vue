<template>
    <div class="Hook">
        <h1>Posts</h1><hr>
        <input type="text" v-model="searchTerm" placeholder="Search">

        <div v-for="post in filtersearch" :key="post.id">
            <h1>{{post.title}}</h1>
            <div class="content">{{post.body | snippet}}</div>
        </div>
    </div>
	
</template>


<script>
import axios from 'axios'
export default {
	name: 'Hook',
	data(){
		return {
            posts:[],
            searchTerm:''
		}
	},
    computed:{
        filtersearch(){
            return this.posts.filter(post=>{
                return post.title.match(this.searchTerm)
            })
        }
    },
    methods: {
        
    },
    created() {
        axios.get('https://jsonplaceholder.typicode.com/posts')
        .then((response) => {
            console.log(response)
            this.posts=response.data
        }).catch((error) => {
            console.log(error)
            
        });
    },
    
}	 
</script>

<style scoped>
	h1{
        color: rgb(31, 187, 57);
        text-align: center;
    }
	
</style>