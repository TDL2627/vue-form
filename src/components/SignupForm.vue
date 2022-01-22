<template>
  <form> 
<label>Email</label>
<input type="email" v-model="email">

<label>Password:</label>
<input type="password" v-model="password">

<label>Role:</label>
<select v-model="role" required>
  <option value="Mentor">Mentor</option>
  <option value="Mentee">Mentee</option>
</select>



<label>Skills: Press Alt  , </label>
<input type="text" v-model="tempSkill" @keyup="addSkill">
<div class="pill" v-for="skill in skills" :key="skill">
{{skill}}
</div>


<div class="terms">
 <input type="checkbox" v-model="terms" required>
 <label >Accept Terms and Conditions
 </label>
</div>

<input type="checkbox" value="Dax" v-model="names">
<label >Dax</label>
<input type="checkbox" value="Palesa" v-model="names">
<label >Palesa</label>
<input type="checkbox" value="Ghost" v-model="names">
<label >Ghost</label>
  </form>


  <p>Email: {{email}}</p>
  <p>Password: {{password}}</p>
  <p>Role: {{role}}</p>
  <p>Terms and Conditions : {{terms}}</p>
  <p>Names:{{names}}</p>
</template>

<script>
export default {
  data(){
    return{
      email:"",
      password:"",
      role:"",
      term:false,
      names:[],
      skills:[]
    }
  },
  methods:{
    addSkill(e){
      if(e.key === "," && this.tempSkill){
        this.skills.push(this.tempSkill);
        this.tempSkilll="";
      }
    }
  }

}

</script>

<style>
form {
    max-width: 420px;
    margin: 30px auto;
   
    text-align: left;
    padding: 40px;
    border-radius: 10px;
}
label {
    color: #aaa;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
}
input {
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

.pill {
  display: inline-block;
  margin: 20px 10px 0 0;
  padding: 6px 12px;
  background: #eee;
  border-radius: 20px;
  font-size: 12px;
  font-weight: bold;
  color: #777;
  cursor: pointer;
}

</style>