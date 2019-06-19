---
layout: single
title:  "Simple Python Email Server"
excerpt: "Simple python email server that uses a gmail account to send emails"
date:   2019-06-18 10:00:00 -0500
search: true
toc: true
toc_sticky: true
categories:
  - projects
tags:
  - Python
  - Flask
  - yagmail
  - heroku
---

For a side project I wanted to be allow users to be able to send me emails but I didn't want to use a third party service or have my email in a mailto in the client so I made this small email api.

## Link to the code

[email-server](https://github.com/scott-mcnulty/email-server){:target="_blank"}

## Set up

Create a virtual environment and install the packages:

```sh
virtualenv venv;

source venv/bin/activate;

pip install -r requirements.txt
```

Follow [this guide](https://blog.macuyiko.com/post/2016/how-to-send-html-mails-with-oauth2-and-gmail-in-python.html) to create oauth2 gmail account credentials.

Open the  `make_credentials.py` script and replace `YOUR_EMAIL_HERE` with the gmail email you want to use. Run the script to have `yagmail` create your oauth2 gmail client credentials file.

```sh
python3 scripts/make_credentials.py
```

Now you can run the main application!

```sh
./run.sh
```

## Sending an email

Hit the `/email` endpoint with a `POST` request using something like the example JSON below:

```json
{
    "from": "test@test.com",
    "subject": "This is a test email",
    "content": "Here is the email content!"
}
```

## Deploying to Heroku

If you have a Heroku account this email server can be deployed there using the shell deployment scripts in the scripts directory. Install the Heroku cli and log in. Next change the `APP_NAME_HERE` values from the shell scripts in the scripts directory with your application name. Lastly follow the steps below:

Build the app

```sh
./scripts/build-app.sh
```

Then release it

```sh
./scripts/release-app.sh
```
