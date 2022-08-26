<template>
    <div class="about">
        <h1>Hello {{their_name}},this is about.vue</h1>
<p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Ipsum ex voluptatem unde dolor asperiores exercitationem voluptate iste ab aspernatur placeat dolores ipsam, nobis ullam nostrum saepe quas quam enim alias?</p>
    </div>
</template>
<script>

export default {
    name:'Skills',
    data() {
        return{
their_name:this.$route.params.name
        }
    }
}
</script>
