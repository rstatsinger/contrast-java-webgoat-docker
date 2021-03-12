# JUMPSTART DEVSECOPS and SECURITY OBSERVABILITY - for FREE - with the Contrast Community Edition, WebGoat, and Docker

## Got a little Docker experience? This will be easy.

CLONE THIS REPO (or just grab all the files)

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
	- Click the dropdown next to your name and go to your User Settings page:

GET READY…

<img src="img/CESetup6.png" width=500px />

<img src="img/CESetup7.png" width=500px />

Click Profile on the left. Copy the API Key, Service Key, and User Name from the
Profile page to the `./Docker/.env.template` file like so:

```
CONTRAST__API__USER_NAME=<your-user-name>
CONTRAST__API__API_KEY=<your-api-key>
CONTRAST__API__SERVICE_KEY=<your-service-key>
```

Then rename .env.template to .env

GET SET…

GO!

```shell
docker-compose run --rm webgoat
```

<img src="img/CESetup10.png" width=500px />

<img src="img/CESetup11.png" width=154px />

## You should be good to go! Next, crack open the [Lab Guide](https://github.com/rstatsinger/IASTRASPLab/blob/master/WebGoatLab.pdf)

<img src="img/CESetup12.png" width=500px />

