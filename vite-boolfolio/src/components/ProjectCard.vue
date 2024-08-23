<script>
export default {
    data() {
        return {
        }
    },
        props: {
    author: {
        type: String,
        required: true,
    },
    title: {
        type: String,
        required: true,
    },
    content: {
        type: String,
        required: true,
    },
    image: {
        type: String,
        required: true,
    }
    }
}
</script>

<template>
    <article class="card">
        <h1>{{ title }}</h1>
        <h3>{{ author }}</h3>
        <img :src="image" alt="Project Image" class="project-image" />
            <p>{{ content }}</p>
    </article>
</template>

<style scoped>

.project-image {
    max-width: 500px;
    height: 500px;
    border-radius: 8px;
    margin-bottom: 16px;
}
.card {
    background-color: #a6f7de;
    border: 1px solid #e0e0e0;
    border-radius: 8px;
    padding: 16px;
    margin: 16px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
    transform: translateY(-5px);
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
}

h1 {
    font-size: 1.5em;
    color: #333333;
    margin-bottom: 8px;
}

h3 {
    font-size: 1em;
    color: #777777;
    margin-bottom: 16px;
}

p {
    font-size: 0.9em;
    color: #555555;
    line-height: 1.6;
}

</style>