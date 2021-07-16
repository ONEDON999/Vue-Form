<template>
  <form @submit.prevent="handleSubmit">
      <label >Email:</label>
      <input type="email" required v-model="email">

      <label >Password</label>
      <input type="password" required v-model="password">
      <div v-if="passwordError" class="error">{{passwordError}}</div>

      <label >Role</label>
      <select v-model="role">
          <option value="developer">web Developer</option>
          <option value="designer">wed Designer</option>
      </select>

      <label >Skills</label>
      <input type="text" v-model="temSkill" @keyup.alt="addSkill" placeholder="enter and press alt key + comma key">
      <div v-for="skill in skills" :key="skill" class="pill">
          <span @click="deleteSkill(skill)"> {{skill}} </span> 
      </div>
      
      <div class="terms">
          <input type="checkbox" required v-model="terms">
          <label>Accept terms and conditions</label>
      </div>

        <div class="submit">
            <button>Create an Account</button>
        </div>
      <!-- <div>
          <input type="checkbox" value="shaun" v-model="names">
          <label >Shaun</label>
      </div>
      <div>
          <input type="checkbox" value="Don" v-model="names">
          <label >Don</label>
      </div>
      <div>
          <input type="checkbox" value="Nii" v-model="names">
          <label >Nii</label>
      </div> -->
  </form>
 
   <!-- <p>Names: {{names}}</p> -->
</template>

<script>
export default {
    data(){
        return{
            email: '',
            password: '',
            role: 'developer',
            terms: false,
            names: [],
            temSkill: '',
            skills:[],
            passwordError: ''
        }
    },
    methods:{
        addSkill(e){
            if(e.key ===',' && this.temSkill){
                if(!this.skills.includes(this.temSkill)){
                    this.skills.push(this.temSkill)
                }
                
                this.temSkill=''
            }
        },
        deleteSkill(skill){
            this.skills = this.skills.filter((item) => {
                return skill !==item
            })
        },
        handleSubmit(){
            //validate password
            this.passwordError=this.password.length > 5 ?
            '' : 'Password must be at least 6 chars length'
            
            if(!this.passwordError){
                console.log('email',this.email)
                console.log('password',this.password)
                console.log('role',this.role)
                console.log('skills',this.skills)
                console.log('terms',this.terms)
            }
        }
    }
}
</script>

<style>
form{
    max-width: 420px;
    margin: 30px auto;
    background: white;
    text-align: left;
    padding: 40px;
    border-radius: 10px;
}label{
    color: #aaa;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
}input,select{
    display: block;
    padding: 10px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #ddd;
    color: #555;

}input[type="checkbox"]{
    display: inline-block;
    width: 16px;
    margin: 0 10px 0 0;
    position: relative;
    top: 2px;
}
.pill{
    display: inline-block;
    margin: 20px 10px 0 0;
    padding: 6px 12px;
    background: #eee;
    border-radius: 20px;
    font-size: 12px;
    letter-spacing: 1px;
    font-weight: bold;
    color: #777;
    cursor: pointer;
}button{
    background: #0b6dff;
    border: 0;
    padding: 10px 20px;
    margin-top: 20px;
    color: white;
    border-radius: 20px;
}.submit{
    text-align: center;
}.error{
    color: #ff0062;
    margin-top: 10px;
    font-size: 0.8em;
    font-weight: bold;
}
</style>