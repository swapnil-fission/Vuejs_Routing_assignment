// eslint-disable-next-line
/* eslint-disable */
<template>
  <div>
    <Sidemenu />
    <h1>Contactus Form</h1>
    <div class=container>
      <form>
        <label for="fname">First Name</label>
        <input
          type="text"
          id="fname"
          name="firstname"
          placeholder="Your name.."
        />

        <label for="lname">Last Name</label>
        <input
          type="text"
          id="lname"
          name="lastname"
          placeholder="Your last name.."
        />

        <label for="country">Country</label>
        <select id="country" name="country">
          <option value="australia">Australia</option>
          <option value="canada">Canada</option>
          <option value="usa">USA</option>
        </select>

        <label for="subject">Subject</label>
        <textarea
          id="subject"
          name="subject"
          placeholder="Write something.."
          style="height: 200px"
        ></textarea>

        <input class="submitbutton" type="submit" value="Submit" />
      </form>
    </div>
    <table>
      <tr>
        <td>ID</td>
        <td>City</td>
        <td>Job</td>
      </tr>
      <tr v-for="user in users" :key="user.id">
        <td>{{ user.id }}</td>
        <td>{{ user.city }}</td>
        <td>{{ user.job }}</td>
      </tr>
    </table>
    <h1 v-if='show'>This is conditional rendering</h1>
    <h1 v-else>Error msg on conditional rendering</h1>
    <button v-on:click='display'>toggle button</button>
    <Header />
  </div>
</template>
<script>
import Header from '../components/Header.vue'
import Sidemenu from '../components/Sidemenu.vue'
export default {
  name: 'Contactus',
  components: {
    Header,
    Sidemenu
  },
  data () {
    return {
      show: true,
      users: [
        { id: 1, city: 'Nagpur', job: 'IT' },
        { id: 2, city: 'Delhi', job: 'help desk' },
        { id: 3, city: 'Mumbai', job: 'QA' },
        { id: 4, city: 'Pune', job: 'SDE' },
        { id: 5, city: 'Nagar', job: 'SA' }
      ]
    }
  },
  methods: {
    display () {
      this.show = !this.show
    }
  }
}
</script>
<style scoped>
label {
  float: left;
}
.container {
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
}

input[type="text"],
select,
textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  margin-top: 6px;
  margin-bottom: 16px;
  resize: vertical;
}
.submitbutton {
  background-color: red;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
</style>
