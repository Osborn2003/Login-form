<!DOCTYPE html>
<html lang = "en">
  <head>
    <meta charset="UTF-8">
    <meta name = "viewport" content = "width= device-width, initial-scale = 1.0">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.min.css">
    <style>
        *{
          margin:0;
          padding:0;
          box-sizing:border-box;
        }
        body {
          height:100vh;
          width: 100%;
          background:rgba(30, 30, 30, 1);
          color: #ff22ff;
          display:flex;
          justify-content:space-evenly;
          align-items: center;
          position: relative;
        }
        .container {
          display: flex;
          align-items: center;
          background:linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.1));
          backdrop-filter:blur(5px);
          box-shadow: 2px 2px 5px #000;
          border-radius: 1rem;
          position: relative;
          min-height: 500px;
          width:40%;
          flex-direction:column;
          justify-content: space-evenly;
          z-index: 1;
        }
        .container .form {
          width: 90%;
        }
        .container .form-title {
          width: 100%;
          text-align: center;
        }
        .container .form input{
          width: 100%;
          height: 3rem;
        }
        .container .form label {
          font-weight: 700;
        }
        .container .form .input {
          background: transparent;
          outline:none;
          border:none;
          border-radius: 5px;
          backdrop-filter: blur(10px);
          padding:.5rem;
        }
        .container .form .input:hover,
        .container .form .input:active {
          border:none;
          border-bottom: 2px solid #ff00ff;
          border-radius: 5px;
          backdrop-filter: blur(10px);
          padding:.5rem;
        }
        .container .form #error-message {
          display:block;
          width:100%;
          color:red;
          font-weight:300;
          font-size:.8rem;
          margin-top:.5rem;
        }
        .container .form label .spanx{
          color:red;
        }
        .container .form #login-btn {
          height: 2.5rem;
          background: white-smoke;
          border:none;
          border-radius: 5px;
          padding:.5rem;
        }
          .container .form #login-btn:active {
            background: linear-gradient( #ff00ff, #ff00ff);
        }
        .ball-1{
          background: linear-gradient(#00ffe6, #ffcd20);
          content:" ";
          height:30%;
          width:50%;
          border-radius:50%;
          position: absolute;
          z-index: -1;
          top:10%;
          left:5%;
         /* flex: 1 200px;*/
        }
        .ball-2{
          background:linear-gradient(#00ffe6, #ff4512);
          content:" ";
          height:30%;
          width:50%;
          border-radius:50%;
          z-index: -1;
          position: fixed;
         /* flex: 1 200px;*/
          bottom:10%;
          right: 5%;
        }
        .container .social-signIn {
          display: flex;
          justify-content:space-evenly;
          align-items:center;
          gap:.5rem;
          width:90%;
          border-radius: 5px;
        }
        .container .social-signIn .social-signIn-icon{
          background: linear-gradient(rgba(255, 255, 255, 0.2), rgba(255, 255, 255, 0.2));
          backdrop-filter: blur(10px);
          text-align: center;
          padding: .5rem;
          height:2rem;
          width:50%;
        }
            .container .social-signIn .social-signIn-icon span{
              width:5px;
              height:5px;
              margin:.5rem;
            }
        @media (max-width:610px) {
          .container {
            min-width:90%;
          }
        }
    </style>
  </head>
  <body>
          <div class="ball-1"></div>
          <div class="ball-2"></div>
      <div class="container el">
        <h1 class="form-title">Login Here</h1>
        <div class="form" id="form">
          <label><span class="spanx" id="span1" style="color:red; display:none;">*</span> Username </label><br/>
          <input type="text" class="input" id="username" placeholder="Email or Phone" required>
          <br/><br/>
          <label><span class="spanx" id="span2" style="display:none;">*</span> Password </label><br/>
          <input type="password" class="input" id="password" placeholder="Password" required>
          <p id="error-message"></p>
          <br/>
          <input type="submit" onclick="Function()" value="Login" id="login-btn">
        </div>  
          <div class="social-signIn">
            <div class="social-signIn-icon"><span><i class="bi bi-google"></i></span>Google</div>
            <div class="social-signIn-icon"><span><i class="bi bi-facebook"></i></span>Facebook</div>
          </div>
      </div>
      <script type="text/javascript">
          let Function = function(){
            let username = document.getElementById("username").value;
            let password = document.getElementById("password").value;
            let error_message = document.getElementById("error-message");
            let span1 = document.getElementById("span1");
            let span2 = document.getElementById("span2");
            if (!username || !password) {
              error_message.innerHTML = "Error: Please fill-in your username & password";
                if (!username && password) {
                  span1.style.display = 'inline-block';
                  span2.style.display = 'none';
                }else if (username && !password) {
                  span1.style.display = 'none';
                  span2.style.display = 'inline-block';
                }else {
                  span1.style.display = 'inline-block';
                  span2.style.display = 'inline-block';
                }
            }else{
              alert("Login Successful")
            }
          }
      </script>
  </body>
