<!-- <template>
  <div id="signup">
    <div ref="signupModal"></div>
    <button @click="showSignupModal">Sign Up</button>
  </div>
</template>

<script>
import firebase from "firebase/compat/app"; // updated import statement
import "firebase/compat/auth"; // updated import statement
import firebaseui from "firebaseui"; 

export default {
  methods: {
    showSignupModal() {
      console.log(firebase.auth()); // to check if firebase.auth() returns a valid object

      const ui = new firebaseui.auth.AuthUI(firebase.auth());
      ui.start("#signupModal", {
        signInOptions: [
          firebase.auth.EmailAuthProvider.PROVIDER_ID,
          firebase.auth.GoogleAuthProvider.PROVIDER_ID,
          firebase.auth.FacebookAuthProvider.PROVIDER_ID,
        ],
        callbacks: {
          signInSuccessWithAuthResult: function (authResult, redirectUrl) {
            console.log('authResult:', authResult);
            console.log('redirectUrl:', redirectUrl);
            return false;
          },
        },
        signInFlow: "popup",
        credentialHelper: firebaseui.auth.CredentialHelper.NONE,
      });
    },
  },
};
</script>  -->
