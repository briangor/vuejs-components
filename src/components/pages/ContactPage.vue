<template>
    <div class="contact">
        <h5>Contact</h5>

        <form>
            <div class="mb-3">
                <label for="name" class="form-label">Name</label>
                <input type="text" v-model="name" class="form-control" id="name" aria-describedby="nameHelp">
            </div>
            <div class="mb-3">
                <label for="email" class="form-label">Email address</label>
                <input type="email" v-model="email" class="form-control" id="email" aria-describedby="emailHelp">
            </div>
            <div class="mb-3">
                <label for="message" class="form-label">Message</label>
                <textarea name="message" v-model="message" id="message" class="form-control" cols="30" rows="6"></textarea>
            </div>
            <div class="mb-3 form-check">
                <input type="checkbox" class="form-check-input" id="checkbox">
                <label class="form-check-label" for="checkbox">Subscribe to the newsletter</label>
            </div>
            <button type="submit" class="btn btn-outline-primary">Submit</button>
        </form>

        <div class="mt-4 border p-2">
            <h5>The Form Data</h5>
            <p>Name: {{  name  }}</p>
            <p>Email: {{  email  }}</p>
            <p>Message: {{  message  }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ContactPage',
    data() {
        return {
            name: '',
            email: '',
            message: ''            
        }
    }

}
</script>
<style lang="scss">
</style>