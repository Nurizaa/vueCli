<template>
    <div>
        <div v-for="item in info.data">
            <h1>{{item.ID}}</h1>
            <h2>{{item.FileName}}</h2>
            <h2>{{item.Descr}}</h2>
            <video width="450" controls :src="item.Path"></video>
            <hr>
        </div>
    </div>
</template>

<script>
    import axios from 'axios'

    export default {
        el: '#test',
        data() {
            return {
                info: null
            };
        },
        mounted() {
            axios
                .get('http://ctmax.d-oracle.com/videos/')
                .then(response => (this.info = response));
        }
    };
</script>