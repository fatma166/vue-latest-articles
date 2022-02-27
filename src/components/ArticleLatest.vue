<template>
    <div>
     
        <div class="card mb-2" v-for="article in articles" v-bind:key="article.id">
            <div class="card-body ">
               
                <h4 class="card-title">{{ article.title }}</h4>
                <div class="card-img"><img src="{{ article.img }}"/></div>
                <p class="card-text">{{article.description }}</p>
            </div>
        </div>


    </div>
</template>

<script>

    export default {
        data() {
            return {
                articles:[]
            };
        },

        created() {
            this.getArticles();
        },

        methods: {
            getArticles(api_url) {
                api_url = 'http://jsonplaceholder.typicode.com/posts';
                 fetch(api_url)
                    .then(response => response.json())
                    .then(data => (this.articles = data));

                        
           }
        },


    };
</script>