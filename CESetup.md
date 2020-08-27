
# JUMPSTART DEVSECOPS and SECURITY OBSERVABILITY - for FREE - with the Contrast Community Edition, WebGoat, and Docker

## Got a little Docker experience? This will be easy.

CLONE THIS REPO (or just grab all the files)

	- Create a working directory
	- Stash everything there
	- Make a backup copy of the Dockerfile

SIGN UP FOR A Contrast Community Edition Account [here](https://bit.ly/341PrFu)
	- Check your email for confirmation

<img src="img/CESetup0.png" width=500px />

<img src="img/CESetup1.png" width=500px />

CONFIRM YOUR ACCOUNT….

	- Confirm your new account from registration email
	- Click Confirm Account to set your password

<img src="img/CESetup2.png" width=500px />

GET STARTED…

	- Click Get Started
	- Agree to the Ts & Cs
	- Click Start Agent Setup

<img src="img/CESetup3.png" width=500px />

<img src="img/CESetup4.png" width=500px />

<img src="img/CESetup5.png" width=450px />

	- Click the x at the top right so that you see the main dashboard
	- Click the dropdown next to your name and go to the Your Account page:

GET READY…

<img src="img/CESetup6.png" width=500px />

<img src="img/CESetup7.png" width=500px />

	- Plug the Organization ID, Authorization Header, and API Key from the Your Account page into the proper locations in the Dockerfile
  	- Note: this is not best practice but we want to be expedient
	- Doublecheck for correctness!

GET SET…

<img src="img/CESetup8.png" width=500px />

<img src="img/CESetup9.png" width=154px />

GO!

% docker build \`pwd\` \-tdockerwebgoat

% docker run \-\-rm –p 8080:8080 –tdockerwebgoat

<img src="img/CESetup10.png" width=500px />

<img src="img/CESetup11.png" width=154px />

## You should be good to go! Next, crack open the [Lab Guide](https://github.com/rstatsinger/IASTRASPLab/blob/master/WebGoatLab.pdf)

<img src="img/CESetup12.png" width=500px />

