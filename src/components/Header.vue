<template>
    <header>
        <h1>Task Tracker</h1>

        <Button 
            v-show="homePage"
            @btn-click="$emit('toggle-add-task')"
            :text="showAddTask ? 'Close' : 'Add Task'" 
            :color="showAddTask ? 'Red' : 'Blue' "/>

    </header>
</template>



<script>
    import Button from './Buttons.vue'

    export default {
        name: 'Header',

        props: {
            showAddTask: Boolean
        },

        components: {
            Button
        },

        computed: {
            homePage() {
                if(this.$route.path === '/') {
                    return true
                } else {
                    return false
                }
            }
        }
    }

</script>




<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-content: center;
        margin-bottom: 20px;
    }

</style>