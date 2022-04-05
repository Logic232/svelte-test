<script context="module">
	import { browser, dev } from '$app/env';

	// we don't need any JS on this page, though we'll load
	// it in dev so that we get hot module replacement...
	export const hydrate = dev;

	// ...but if the client-side router is already loaded
	// (i.e. we came here from elsewhere in the app), use it
	export const router = browser;

	// since there's no dynamic data here, we can prerender
	// it so that it gets served as a static asset in prod
	export const prerender = true;
</script>

<svelte:head>
	<title>About</title>
</svelte:head>

<main>

	<div class="main">  	
		  <input type="checkbox" id="chk" aria-hidden="true">
  
			  <div class="signup">
				  <form>
					  <label for="chk" aria-hidden="true">Sign up</label>
					  <input type="text" name="txt" placeholder="User name" required="">
					  <input type="email" name="email" placeholder="Email" required="">
					  <input type="password" name="pswd" placeholder="Password" required="">
					  <button>Sign up</button>
				  </form>
			  </div>
  
			  <div class="login">
				  <form>
					  <label for="chk" aria-hidden="true">Login</label>
					  <input type="email" name="email" placeholder="Email" required="">
					  <input type="password" name="pswd" placeholder="Password" required="">
					  <button>Login</button>
				  </form>
			  </div>
	  </div>
  </main>
  
<style>
	main{
	margin: 0;
	padding:0;
	display: flex;
	justify-content: center;
	align-items: center;
	min-height: 100vh;
	font-family: 'Jost', sans-serif;
	
}
.main{
	width: 450px;
	height: 500px;
	background: red;
	overflow: hidden;
	background: linear-gradient(to bottom, #85f307, #ff8800, #ff0808);
	border-radius: 10px;
	box-shadow: 5px 20px 50px #000;
}
#chk{
	display: none;
}
.signup{
	position: relative;
	width:100%;
	height: 100%;
}
label{
	color: #fff;
	font-size: 2.3em;
	justify-content: center;
	display: flex;
	margin: 60px;
	font-weight: bold;
	cursor: pointer;
	transition: .5s ease-in-out;
}
input{
	width: 60%;
	height: 40px;
	background: #e0dede;
	justify-content: center;
	display: flex;
	margin: 20px auto;
	padding: 10px;
	border: none;
	outline: none;
	border-radius: 5px;
}
button{
	width: 60%;
	height: 32px;
	margin: 10px auto;
	justify-content: center;
	display: block;
	color: #fff;
	background: #573b8a;
	font-size: 1em;
	font-weight: bold;
	margin-top: 20px;
	outline: none;
	border: none;
	border-radius: 5px;
	transition: .2s ease-in;
	cursor: pointer;
	
}
button:hover{
	background: #6d44b8;
}
.login{
	
	height: 460px;
	background: #ffffff;
	border-radius: 12px;
	transform: translateY(-180px);
	transition: .8s ease-in-out;
}
.login label{
	color: #573b8a;
	transform: scale(.6);
}

#chk:checked ~ .login{
	transform: translateY(-500px);
}
#chk:checked ~ .login label{
	transform: scale(1);	
}
#chk:checked ~ .signup label{
	transform: scale(.6);
}
</style>
