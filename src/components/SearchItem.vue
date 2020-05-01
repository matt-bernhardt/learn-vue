<template>
    <li class="search-item">
        <h3><a :href="external_link">{{ title }}</a></h3>
        <p>Date: {{ publication_date }}</p>
        <p>{{ description }}</p>
        <p>{{ content_type }}</p>
    </li>
</template>

<script>
export default {
    props: {
        result: Object,
        type: String,
    },
    computed: {
        content_type: function() {
            return this.result.content_type || "";
        },
        description: function() {
            return ( this.result.summary ? this.result.summary[0] : "" );
        },
        external_link: function() {
            return this.result.source_link || this.result.sourceLink;
        },
        publication_date: function() {
            return this.result.publication_date || this.result.publicationDate;
        },
        title: function() {
            return this.result.title;
        }
    }
}
</script>

<style scoped>
li.search-item {
    border: 1px solid #696969;
    list-style-type: none;
    padding: 0.5rem;
    margin-bottom: 1rem;
    text-align: left;
}
</style>
