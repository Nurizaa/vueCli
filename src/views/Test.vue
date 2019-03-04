<template>
    <div >
        <h1 v-for="item in info.data">{{item.ID}}</h1>
    </div>
    <!--<p>-->
        <!--{{info}}-->
    <!--</p>-->
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