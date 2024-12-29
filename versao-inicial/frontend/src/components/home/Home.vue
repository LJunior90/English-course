<template>
    <div class="home">
        <PageTitle icon="fa fa-home" main="Dashboard"
            sub="Let's Practice" />
    </div>
    <div class="stats">
        <Stat title="Categorias" :value="stat.categories"
            icon="fa fa-folder" color="#d54d50"/>
        <Stat title="Artigos" :value="stat.articles"
            icon="fa fa-file" color="#3bc460"/>
        <Stat title="Usuários" :value="stat.users"
            icon="fa fa-user" color="#3282cd"/>
    </div>
</template>

<script>
import PageTitle from '@/components/template/PageTitle'
import Stat from './Stat'
import Axios from 'axios'
import { baseApiUrl } from '@/global'
export default {
    name: 'Home',
    components: { PageTitle, Stat },
    data: function() {
        return {
            stat: {}
        }
    },
    methods: {
        getStats() {
            Axios.get(`${baseApiUrl}/stats`).then(res => this.stat = res.data)
        }
    },
    mounted() {
        this.getStats() 
    }

}
</script>

<style>

</style>