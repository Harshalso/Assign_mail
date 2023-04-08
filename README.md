# Assign_mail
<!DOCTYPE html>
  <head>
    <title>Login/Logout Example</title>
  </head>
  <body>
  <p> <iframe src="https://bvieer.maps.arcgis.com/apps/instant/basic/index.html?appid=3d5fb0002185465abc6e61612f5fe8f0&locale=en-US" width="1400" height="1000" frameborder="0" style="border:0" allowfullscreen>iFrames are not supported on this page.</iframe> </p>
    <label for="email">Email:</label>
    <input type="text" id="email" placeholder="Enter email">
    <br><br>
    <label for="password">Password:</label>
    <input type="password" id="password" placeholder="Enter password">
    <br><br>
    <button id="login">Login</button>
    <button id="logout">Logout</button>
    <br><br>
    <p id="status1">status: Logged out</p>
    <script>
      class User {
    constructor(email, password) {
      this.email = email;
      this.password = password;
      this.loggedIn = false;
    }
    
    login() {
      this.loggedIn = true;
    }
    
    logout() {
      this.loggedIn = false;
    }
  }
  
  const user = new User("programming@gmail.com", "assignment9");
  
  const loginBtn = document.getElementById("login");
  const logoutBtn = document.getElementById("logout");
  const status1 = document.getElementById("status1");
  
  loginBtn.addEventListener("click", () => {
    const email = document.getElementById("email").value;
    const password = document.getElementById("password").value;
    if (email === user.email && password === user.password) {
      user.login();
      console.log("login");
      status1.textContent = `status1: Logged in as ${user.email}`;
    } else {
      alert("Invalid email or password!");
    }
  });
  
  logoutBtn.addEventListener("click", () => {
    user.logout();
    status1.textContent = "status1: Logged out";
  });
    </script>
  </body>
</html>
