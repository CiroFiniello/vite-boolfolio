<script>
import axios from 'axios';
import ProjectCard from './ProjectCard.vue';

export default {
    components : {
        ProjectCard
    },
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
<!-- <ul>
    <li v-for="project in projects" :key="project.id">
        {{ project.title }}
    </li>
</ul> -->
<ProjectCard
v-for="project in projects"
:key="project.id"
:author="project.author"
:title="project.title"
:content="project.content"
:image="project.image"
/>

</template>

<style scoped>
body {
    font-family: 'Arial', sans-serif;
    background-color: #f5f5f5;
    color: #333333;
    margin: 0;
    padding: 0;
}

#app {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
}

</style>