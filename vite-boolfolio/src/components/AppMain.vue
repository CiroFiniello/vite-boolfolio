<script>
import axios from 'axios';

export default {
    data() {
        return {
            projects: [],  // Assicurati che sia 'projects'
        }
    },
    methods:{
        getProjects(){
            axios.get('http://127.0.0.1:8000/api/project', {
    params: {
        }
    })
    .then((response) =>{
        console.log(response.data.results);
        this.projects = response.data.results; // Corretto da 'this.project' a 'this.projects'
    })
    .catch(function (error) {
        console.log(error);
    })
    .finally(function () {
        // always executed
    });  
        }
    },
    created(){
        this.getProjects();
    }
}
</script>

<template>
<ul>
    <li v-for="project in projects" :key="project.id">
        {{ project.title }}
    </li>
</ul>
</template>

<style scoped>

</style>