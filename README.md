JARNHS BLOG
<!DOCTYPE html><html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>JARNHS WEBSITE</title>
<style>
body{font-family:Arial, sans-serif;margin:0;background:#f4f6f9}
header{background:#0b5ed7;color:#fff;padding:10px;text-align:center}
.container{padding:15px}
.hidden{display:none}
input,select,textarea,button{width:100%;padding:8px;margin:6px 0}
button{background:#0b5ed7;color:white;border:none;border-radius:5px}
.card{background:white;padding:10px;border-radius:8px;margin-bottom:10px}
img.post-img{max-width:100%;border-radius:6px}
.author{cursor:pointer;color:#0b5ed7;font-weight:bold}
footer{text-align:center;padding:10px;background:#eee}
</style>
</head>
<body>
<header>
<h2>JARNHS WEBSITE</h2>
<img id="logo" src="logo.png" style="max-height:60px" />
</header><div class="container"><!-- LOGIN --><div id="loginBox" class="card">
<h3>Login</h3>
<input id="loginName" placeholder="Your name" />
<select id="loginRole">
<option value="student">Student</option>
<option value="teacher">Teacher</option>
</select>
<button onclick="login()">Enter</button>
<p>Students only: <a href="#" onclick="showSignup()">Sign up here</a></p>
</div><!-- SIGNUP --><div id="signupBox" class="card hidden">
<h3>Student Sign Up</h3>
<input id="suName" placeholder="Full name" />
<input id="suAge" placeholder="Age" />
<input id="suStrand" placeholder="Strand" />
<button onclick="signup()">Create account</button>
<button onclick="showLogin()">Back</button>
</div><!-- HOME --><div id="homeBox" class="hidden">
<div class="card">
<h3>Welcome, <span id="currentUser"></span></h3>
<button onclick="showCreatePost()">Create Blog</button>
<button onclick="logout()">Logout</button>
</div><div class="card">
<h4>Authors</h4>
<div id="authorList"></div>
</div><div id="postsBox"></div>
</div><!-- CREATE POST --><div id="createBox" class="card hidden">
<h3>Create Blog</h3>
<input id="postTitle" placeholder="Title" />
<textarea id="postText" placeholder="Write your blog..."></textarea>
<input type="file" id="postImage" accept="image/*" />
<button onclick="savePost()">Publish</button>
<button onclick="backHome()">Cancel</button>
</div></div><footer>
Created by "MD. Quintero"
</footer><script>
let users = JSON.parse(localStorage.getItem('jarnhs_users')||'[]');
let posts = JSON.parse(localStorage.getItem('jarnhs_posts')||'[]');
let session = JSON.parse(localStorage.getItem('jarnhs_session')||'null');

function showSignup(){
 document.getElementById('loginBox
