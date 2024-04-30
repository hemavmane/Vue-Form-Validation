<template>
<div class="container">
    <h1 class="title">Vue Form Validation</h1>
    <form @submit.prevent="submitForm" class="form">
        <div class="form-group">
            <label for="mobile" class="label">Mobile Number:</label>
            <input type="text" id="mobile" v-model="mobileNumber" class="input" />
        </div>
        <div class="form-group">
            <label for="website" class="label">Website:</label>
            <input type="text" id="website" v-model="website" class="input" />
        </div>
        <button type="submit" class="submit-btn">Submit</button>
    </form>
</div>
</template>

<script>
export default {
    data() {
        return {
            mobileNumber: "",
            website: ""
        };
    },
    methods: {
        submitForm() {
            if (this.mobileNumber.startsWith("0")) {
                this.mobileNumber = this.mobileNumber.substring(1);
            }

            if (this.website.startsWith("http://")) {
                this.website = this.website.substring(7);
            }
        }
    }
};
</script>

<style scoped>
.container {
    max-width: 400px;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    text-align: center;
    /* Align everything inside the container */
}

.title {
    font-size: 24px;
    margin-bottom: 20px;
}

.form {
    display: inline-block;
}

.form-group {
    margin-bottom: 15px;
    text-align: left;
}

.label {
    font-size: 18px;
}

.input {
    width: calc(100% - 20px);
    padding: 10px;
    font-size: 16px;
    border: 1px solid #ccc;
    border-radius: 5px;
}

.submit-btn {
    width: 100%;
    padding: 10px;
    font-size: 18px;
    color: #fff;
    background-color: #007bff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
}

.submit-btn:hover {
    background-color: #0056b3;
}
</style>
