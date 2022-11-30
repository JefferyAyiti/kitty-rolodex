<template>
    <div class="card-container">
        <img 
        :src="source"
        :alt="desc">
        <h3>{{name}}</h3>
        <h4>{{email}}</h4>
    </div>
</template>

<script>
    export default {
        name: 'Card',

        props: ['name', 'email', 'id'],

        data() {
            return{
                source:`https://robohash.org/${this.id}?set=set4&size=180x180`,
                desc: `${this.name} kitty`
            
            }

        }
    }
</script>

<style lang="css" scoped>
.card-container {
  display: flex;
  flex-direction: column;
  background-color: #de9ee7;
  border: 3px solid rgb(213, 135, 46);
  border-radius: 5px;
  padding: 25px;
  cursor: pointer;
  -moz-osx-font-smoothing: grayscale;
  backface-visibility: hidden;
  transform: translateZ(0);
  transition: transform 0.25s ease-out;
}

.card-container:hover {
  transform: scale(1.05);
}

</style>