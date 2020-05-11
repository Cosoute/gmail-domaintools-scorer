
# Gmail Domaintools Risk Scorer

## Overview
This repo contains the project for creating a chrome extension to score your gmail email using the domaintools "risk scorer" functionality.  This project uses code from the [gmail.js](https://github.com/KartikTalwar/gmail.js/) library.

### Requirements
In order for this project to run, you must have a Domaintools account - with access to the Domaintools APIs (an optional Domaintools package that you need to make sure to subscribe to). The particular API that we will be using in this code is the Risk Score API call - which requires you to feed in a domain name. However, the API can also take malformed items - such as email addresses - and is intelligent enough to strip out the domain so that it can properly score it. This code is sloppy and just passes the entire email address of the email sender to the API - and seems to work fine.

You also need to make sure you turn on CORS (cross object domain requests) otherwise the browser will block it. Since we will be making calls to Domaintools from within Gmail. So, prior to running this project, you will need to get a CORS extension for Chrome and make sure it is running. I use the Moesif Orign & CORS Changer for the purpose of this project and made sure to white-list the domaintools.com domain.

## Usage

### First get the code and build it:

````
# get code
git clone https://github.com/cosoute/gmail-domaintools-riskscorer/

# get deps and build
cd gmail-domaintools-riskscorer
npm install

# ensure you're running latest version!
npm update

# make sure you can build the project
npm run build
````

### Now ensure the code loads and works:

* Load the folder containing the extension (or `manifest.json`) in
your chrome browser.  You do this by going to "Preferences" -> Extensions -> "Load Unpacked"
The extension should show up in your extensions pane as "Gmail API Extension 1.0".  Notice in the details of the extension that domaintools.com has been whitelisted since the extension will need to make API calls to domaintools to get the score.

### Install the CORS extension as well
Install Moesif Orign & CORS Changer so that your browser doesn't get upset about making calls to domaintools.  
Upon sucessful installation of the moesif extension, Moesif will display a small icon on the top right corner of your browser.  Make sure you select the toggle until it is "ON".  This means htat you have turned on Cross-Object-Domain-Requests - which is needed in order for this extension to work - due to the API calls to domaintools again.

Make sure to go to the advanced settings of the CORS extension and add "api.domaintools.com" as an allowed domain that can accessed within the project.

/Users/jreynolds/Desktop/Screen Shot 2020-05-11 at 9.04.45 AM.png


### Open gmail in a new tab
* Load `mail.google.com` in your browser and open the developer console.


Cheers!
