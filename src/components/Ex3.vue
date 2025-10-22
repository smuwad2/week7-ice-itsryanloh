<script>
    import axios from 'axios';
    export default { 

        // add code here
        data() {
            return {
                moods: ["Happy", "Sad", "Angry"],
                subject: "",
                entry: "",
                mood: "",
                message: ""
            }
        },
        methods: {
            submitPost() {
                console.log('help')
                axios.get("http://localhost:3000/addPost", {
                    params: {
                        subject: this.subject,
                        entry: this.entry,
                        mood: this.mood,
                    }
                }).then(res => {
                    this.message = res.data.message;
                })
            }
        }
    }
</script>

<template>
    <div class="table m-2">
        <h3>Add a New Blog Post</h3>

        Subject: <input type='text' size='30' v-model='subject' required>
        <br>

        Entry: <br>
        <textarea name='entry' cols='80' rows='5' v-model='entry' required></textarea>
        <br>

        Mood:
        <!-- TODO: Build a dropdown list here for selecting the mood -->
        <select v-model="mood">
            <option v-for="mood in moods">{{ mood }}</option>
        </select>
        <br>
        {{ message }}
        <br>

        <br>
        <button @click="submitPost">Submit New Post</button>

        <hr> Click  <a><router-link to="/ViewPosts/">here</router-link></a>  to return to Main Page
       
    </div>
</template>

