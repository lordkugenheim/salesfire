<template>

    <div class="form-group pb-4">
        <input type="text" class="form-control" id="SearchBar" placeholder="Search">
    </div>

</template>

<script>

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

            const json = await response.json();
            console.log(json);
        } catch (error) {
            console.error(error.message);
        }

    }

    getData();

</script>
