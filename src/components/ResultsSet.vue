<template #default>

<div class="d-flex flex-wrap">

    <template v-for="(item, index) in items.products" v-bind:key="index">

        <div class="card text-center m-1">

            <div class="card-body">

                <img class="" v-bind:src="item.image_url">

                <h5 class="card-text">
                    {{ item.title }}
                </h5>

                <p class="fw-bold">
                    From: £{{ item.price.min.toLocaleString("EN-GB") }}
                </p>            

                <a href="#" class="btn btn-dark w-100">View</a>

            </div>

        </div>

    </template>

</div>

</template>

<script setup>

//    import { ref } from 'vue';

    async function getData() {

        const url = "https://aix.salesfire.co.uk/api/searcha";

        var params = {
            client_id : 'dbf1dbc9-a940-48c2-b44b-0bb6dc63924e',
            query : '',
            limit : 4,
            page : 1
        };

        const urlParams = [];

        for (var key in params) {
            urlParams.push(key + '=' + encodeURIComponent(params[key]));
        }

        try {

            const response = await fetch(url + '?' + urlParams.join('&'));

            if (!response.ok) {
                throw new Error(`Response status: ${response.status}`);
            }

            return response.json();

        } catch (error) {
            console.error(error.message);
        }

    }

    const items = await getData();

    console.log(items);

</script>

<style>

li {
    list-style-type: none;
}

img {
    height: auto;
    width: 100%;
}

.card {
    max-width: calc(50% - .50rem);
}

</style>
