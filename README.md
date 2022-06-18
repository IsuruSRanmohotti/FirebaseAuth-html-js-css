

### Below is the javascript code to add additional information.

```
// Fetching the current user
const user = firebase.auth().currentUser;

// Fetching value from a html input fields with id
const displayName = document.getElementById("name").value;
const photoURL = document.getElementById("photo").value;

// Updating additional information
user.updateProfile({
  displayName,
  photoURL
})
```

> To add additional data on `Sign Up`
```
function signUp() {

  // Fetching value from a html input fields with id
  const email = document.getElementById("email").value;
  const password = document.getElementById("password").value;
  
  // Fetching additional informations
  const displayName = document.getElementById("displayName").value;
  const photoURL = document.getElementById("photo").value;
  
  // Performing Sign Up Operation
  firebase.auth().createUserWithEmailAndPassword(email, password)
    .then((userCredential) => {
      // Updating additional information
      const user = userCredential.user;
      user.updateProfile({
        displayName,
        photoURL
      });
    })
};
