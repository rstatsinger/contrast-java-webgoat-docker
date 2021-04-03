
# Security Observability: Hands-On Lab

Too often, efforts to integrate DevOps and security are hamstrung by the lack of observability. Legacy application security simply does not observe the routes software executes and securing and protecting software becomes a guessing game.

In this lab, we will use a deliberately insecure application called WebGoat and the free community edition of Contrast Security to get real-time results on vulnerabilities!

## Getting Started

### Install Docker

We will be using Docker to run WebGoat and the Contrast Security agent in its own container, safely isolating your system. 

#### Windows

Follow the install directions [here](https://docs.docker.com/docker-for-windows/install/). It is important that you ensure that any needed dependencies (such as Hyper-V, virtualization support in BIOS or the Windows Subsystem for Linux) are enabled before you install and run Docker for Windows.

#### Mac

Follow the install directions [here](https://docs.docker.com/docker-for-mac/install/).

#### Linux

If you are on Ubuntu, run the following command:

```
sudo apt install docker.io
```

If you are running another distribution, install `docker.io` or `docker` with your favorite package manager.

### Create an Account with Contrast Security

Go to [https://www.contrastsecurity.com/contrast-community-edition](https://www.contrastsecurity.com/contrast-community-edition) and create a new account. If you have an account already, you can skip ahead to the next step!

Once you create a new account, you will receive an email with a confirmation link. Make sure you click that link and follow the instructions all the way until you reach the welcome page:

<img src="img/CESetup4.png" width=200px />

Click "Get Started" to finish creating your account.

Once your account is created you can click "Start Agent Setup" then click the `X` in the upper-right corner to quit the wizard.

### Download This Repository

Clone or [download the lab files](https://github.com/rstatsinger/IASTRASPLab/archive/refs/heads/master.zip) to your system.

### Copy/Paste Your API Credentials

Open the file called `.env.template` in the lab files and get ready to copy/paste your API credentials from your Contrast Security account. Go to the Contrast Security dashboard online, click on your name (in the upper-right corner), select "Organization" then "API" to find your credentials:

<img src="img/OrgAPI.png" height=200px width=200px />

Copy the values for `Agent Username`, `API Key` and `Agent Service Key` into the `.env.template` file.

Finally, rename the file to `.env`

## Run WebGoat

Open a Command Prompt (Windows) or terminal and go to the lab directory. Run the following command:

```
run
```

You can also run `docker-compose up` directly instead.

The first time will take longer as Docker downloads the resources necessary to build the container. Once it is ready there will be a message like "Browse to http://localhost:8080/WebGoat and happy hacking!"

Open [http://localhost:8080/WebGoat](http://localhost:8080/WebGoat) in your browser and let's keep going!

## Cause Some Trouble!

Now that WebGoat is running you can start to trigger bad behavior. Feel free to play around or follow along in the lab instructions at [Lab-WebGoat.pdf](Lab-WebGoat.pdf).

## View the Results

You can look at the Contrast Security dashboard at any time now and view results under `Applications > WebGoatDocker`

## Questions or Feedback

If you have questions or feedback, please reach out at [robert.statsinger@contrastsecurity.com](mailto:robert.statsinger@contrastsecurity.com).
