
<template>
    <h2>Add users</h2>
    <div v-show="loading">
        <app-loader/>
    </div>
    <div v-show="!loading">
        <div class="form-group mb-3">
            <label>Name</label>
            <input class="form-control" type="text" v-model="user.name">
        </div>

        <div class="form-group mb-3">
            <label>Lastname</label>
            <input class="form-control" type="text" v-model="user.lastname">
        </div>

        <button 
            class="btn btn-primary" 
            @click.prevent="addUser()"
        >Submit</button>
    </div>
</template>

<script setup>
    import postUser from '@/composables/postUser';
    import { reactive } from 'vue';
    // import axios from 'axios';
    // import { useToast } from 'vue-toast-notification';

    // const $toast = useToast();
    // const loading = ref(false);
    const user = reactive({
        name:'',
        lastname:''
    });
    
    const { loading, addUser } = postUser(user);

    // const submitForm = () => {
    //     loading.value = true;   
    //     axios({
    //         method:'POST',
    //         url:'http://localhost:3004/users',
    //         data:user
    //     })
    //     .then(()=>{
    //         $toast.success('Great !!!')
    //     })
    //     .catch(error =>{
    //         $toast.error('Sorry, try again later')
    //     })
    //     .finally(()=>{
    //         loading.value = false;
    //     })
    // }



</script>
