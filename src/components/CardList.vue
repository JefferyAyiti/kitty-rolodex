<template>
    <div class="card-list">
        <div v-for="profile in profiles" :key="profile.id">
            <Card :name="profile.name" :email="profile.email" :id="profile.id" />
        </div>
    </div>

</template>

<script>
import Card from './Card.vue';


export default {
    name: 'CardList',
    props: ['profiles'],

    components: {
        Card,

    }
}
</script>

<style lang="css" scoped>
.card-list {
    width: 85vw;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    gap: 20px;
}
</style>