<template>
    <div class="Hook">
        <h1>{{title}}</h1>
        <button @click="ChangeTitle">Click Me</button>
    </div>
	
</template>


<script>
export default {
	name: 'Hook',
	data(){
		return {
            title:'Hook Main Data'

		}
	},
    methods: {
        ChangeTitle(){
            this.title='Belajjar VueJS'
        }
    },
    beforeMount() {
        //alert('Before Created Hook')
        
    },
    mounted() {
        //alert(' Created Hook')
    },
    beforeUpdate() {
        alert('..Update In Progress')
    },
}	 
</script>

<style scoped>
	
	
</style>