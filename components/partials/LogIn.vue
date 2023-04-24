<!-- eslint-disable vue/no-dupe-keys

<template>
  <v-app>
    <h1>Sign Up or Log In</h1>
    <v-btn @click="showSignUpModal">Sign Up</v-btn>
    <v-btn @click="showLoginModal">Log In</v-btn>
    <v-dialog v-model="showSignUpModal">
      <v-card>
        <v-card-title>Sign Up</v-card-title>
        <v-card-text>
          <v-form>
            <v-text-field label="Name" v-model="name"></v-text-field>
            <v-text-field label="Email" v-model="email"></v-text-field>
            <v-text-field label="Password" v-model="password"></v-text-field>
          </v-form>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="primary" @click="signup">Sign Up</v-btn>
          <v-btn color="secondary" @click="showSignUpModal = false">Cancel</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <v-dialog v-model="showLoginModal">
      <v-card>
        <v-card-title>Log In</v-card-title>
        <v-card-text>
          <v-form>
            <v-text-field label="Email" v-model="email"></v-text-field>
            <v-text-field label="Password" v-model="password"></v-text-field>
          </v-form>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="primary" @click="login">Log In</v-btn>
          <v-btn color="secondary" @click="showLoginModal = false">Cancel</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-app>
</template>
<script>
 import { ref } from 'vue'
// import Vue from 'vue'
import Vuetify from 'vuetify'
import firebase from 'firebase'

export default {
  name: 'App',
  components: {
    // eslint-disable-next-line vue/no-unused-components
    Vuetify,
  },
  data() {
    return {
      // Show the signup modal
      showSignUpModal: false,
      // Show the login modal
      showLoginModal: false,
      // User name
      name: '',
      // User email
      email: '',
      // User password
      password: '',
    }
  },
  methods: {
    // Sign up the user
    async signup() {
      try {
        // Create a new user account
        const userCredential = await firebase
          .auth()
          .createUserWithEmailAndPassword(this.email, this.password);
        // Update the user's profile with their name
        await userCredential.user.updateProfile({
          displayName: this.name,
        });
        // Log the user in
        await firebase
          .auth()
          .signInWithEmailAndPassword(this.email, this.password);
        console.log("User registered successfully:", userCredential.user);
      } catch (error) {
        console.error("Error registering user:", error);
      }
    },
    // Log in the user
    async login() {
      try {
        // Log the user in
        const userCredential = await firebase
          .auth()
          .signInWithEmailAndPassword(this.email, this.password);
        console.log("User logged in successfully:", userCredential.user);
      } catch (error) {
        console.error("Error logging in user:", error);
      }
    },
  },
  setup() {
    // import { ref } from 'vue'

    // Create a ref to track the state of the signup modal
    const showSignUpModal = ref(false);
    // Create a ref to track the state of the login modal
    const showLoginModal = ref(false);

    return {
      // Return the refs to the signup and login modals
      // eslint-disable-next-line vue/no-dupe-keys
      showSignUpModal,
      // eslint-disable-next-line vue/no-dupe-keys
      showLoginModal,
    }
  },
}


</script>


<style>
body {
  margin: 0;
  padding: 0;
}
</style> -->
