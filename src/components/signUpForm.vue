<template>
    <form>
        <label>Email</label>
        <input type="email" required v-model="Email">
        <label>password</label>
        <input type="password" required v-model="password">
        <label>Role:</label>
        <select v-model="role">
            <option value="developer">developer</option>
            <option value="designer">designer</option>
        </select>
        <div class="terms">
            <input type="checkbox" required v-model="terms">
            <label> accept terms and condition </label>
        </div>
        <div>
            <div>
                <input type="checkbox" value="shone" v-model="names">
                <label>shone </label>
            </div>
            <div>
                <input type="checkbox" value="ahmed" v-model="names">
                <label>ahmed </label>
            </div>
            <div>
                <input type="checkbox" value="samy" v-model="names">
                <label>samy </label>
            </div>
            <div>
                <input type="checkbox" value="hany" v-model="names">
                <label>hany </label>
            </div>
            <div>
                <label>skills:</label>
                <input type="text" v-model="tempSkills" @keypress="addskill">
            </div>
            <div>
                <ul>
                    <li v-for="skill in skills" class="bill">
                        {{ skill }}
                    </li>
                </ul>
            </div>
        </div>

        <div>
        </div>
    </form>
    <p> this is Email {{ Email }} </p>
    <p> this is password {{ password }} </p>
    <p> this is role {{ role }} </p>
    <p> this is terms {{ terms }} </p>
    <p> this is terms {{ names }} </p>
</template>


<script>
export default {
    data() {
        return {
            Email: '',
            password: '', // non default option
            role: 'developer',// default option
            terms: 'fasle', // default
            names: [],// default
            skills: [],
            tempSkills: ''
        }
    },
    methods: {
        addskill(e) {
            if (e.key === "Enter" && this.tempSkills) {
                if (!this.skills.includes(this.tempSkills)) {
                    this.skills.push(this.tempSkills)
                    this.tempSkills = ""
                }
                this.tempSkills = ''
            }
        }
    },
}
</script>


<style>
form {
    background-color: white;
    padding: 20px;
    margin: 100px auto;
    text-align: left;
    max-width: 420px;
    border-radius: 10px;
}

label {
    display: inline-block;
    color: #555;
    font-size: 0.6em;
    margin: 25px 0 15px;
    text-transform: uppercase;
    letter-spacing: 2px;
    font-weight: bold;
}

input,
select {
    display: block;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #ddd;
    color: #555;
}

input[type="checkbox"] {
    display: inline-block;
    width: 16px;
    margin: 0 10px 0 0;
    position: relative;
    top: 2px;
}
</style>