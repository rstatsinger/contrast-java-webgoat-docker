
# Security Observability: Hands-On Lab using Contrast Security, Docker, and WebGoat

In this lab, we will use Contrast Security with a deliberately insecure application called WebGoat to jumpstart your DevSecOps journey, hands-on.

## Prerequisites: A Contrast Security account, Docker Desktop, and a web browser

If you don't have a Contrast Security account, you can sign up for a free one-license Community Edition (CE) account [here](https://bit.ly/341PrFu). 

We will be using Docker to run WebGoat in its own container, safely isolating your system. Contrast Security's dynamic security instrumentation will be built into the Docker image, instrumenting WebGoat at startup. This lab has been tested for Docker Desktop on Mac. It will probably work on Linux, too. Windows instructions are below.

If you have trouble - or if you don't and you just want to discuss the results - please reach out to me at robert.statsinger@contrastsecurity.com.

## Setting up Docker

### Docker on Windows

Follow the install directions [here](https://docs.docker.com/docker-for-windows/install/). It is important that you ensure that any needed dependencies (such as Hyper-V, virtualization support in BIOS or the Windows Subsystem for Linux) are enabled before you install and run Docker for Windows.

### Docker on Mac

Follow the install directions [here](https://docs.docker.com/docker-for-mac/install/).

### Docker on Linux

If you are on Ubuntu, run the following command:

```
sudo apt install docker.io
```

If you are running another distribution, install `docker.io` or `docker` with your favorite package manager.

## Lab Setup

### Create an Account with Contrast Security

Sign up [here](https://bit.ly/341PrFu) for the Contrast Community Edition if you dont already have a Contrast account. If you are already a Contrast customer or are in an evaluation with us, you can skip ahead to the next step!

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
