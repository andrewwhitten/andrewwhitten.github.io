---
layout: post
title:  "Salesforce Development with Github Codespaces"
date: 2022-02-09
categories: Salesforce Codespaces
---
# Salesforce Development with Github Codespaces

## Why

The idea of coding in the cloud with Salesforce is compelling for many reasons:

1) Clean environment to build and run your code each time
2) Quickly onboard new developers onto your team
3) Rent CPU cores and RAM just for the time that you need them
4) Use the same environment from different devices throughout the day (MacBook, Desktop PC, iPad, even your phone should you be so inclined)
5) No need to buy an expensive and heavy new MacBook Pro with M1 Max - all the heavy lifting is now in the Cloud
6) Faster to provision working environment for new team members

Salesforce have announced their cloud based development IDE, Code Builder, way back in June 2020. Recent rumors suggested that it might see beta in Spring '22, however there is no mention of it in the new Release Notes. Additionally it isn't clear how much longer it would take to get to GA even if it was released as beta in say Summer '22.

As compelling as Code Builder might sound, GitHub has been offering and improving their equivalent Codespaces product for a while now, and although it isn't designed for Salesforce, it basically works well with most coding requirements today.

## How

The steps to get this up and running are:

**Step 1:** Create a new GitHub Repository - https://github.com/

**Step 2:** Launch a new CodeSpace from your new repository:

<img width="712" alt="Screen Shot 2022-02-08 at 5 33 42 pm" src="https://user-images.githubusercontent.com/41508645/152949211-969eb5ec-a5a0-4703-99e1-db49916f89af.png">

**Step 3:** At this point you will have Visual Studio Code running in the browser, with a terminal in your new Ubuntu Linux machine:

<img width="1014" alt="Screen Shot 2022-02-08 at 5 33 14 pm" src="https://user-images.githubusercontent.com/41508645/152949252-9fa06e8b-8993-4638-a682-2222e075856a.png">

**Step 4:** Set up the Ubuntu machine as per Salesforce SFDX guidelines for an NPM install: https://developer.salesforce.com/docs/atlas.en-us.sfdx_setup.meta/sfdx_setup/sfdx_setup_install_cli.htm#sfdx_setup_install_cli_npm . Afterwards update with ```npm: update --global sfdx-cli```

<img width="983" alt="Screen Shot 2022-02-08 at 7 57 11 pm" src="https://user-images.githubusercontent.com/41508645/152952453-a187c64f-e33b-431d-a186-91a4f0538790.png">

**Step 5:** Create your Salesforce project as normal:

<img width="895" alt="Create Project" src="https://user-images.githubusercontent.com/41508645/153102794-af7c604b-0675-4f7e-a670-13ab4cc0336a.png">

**Step 6:** **WARNING - Access Tokens represent a security risk if you somehow expose them! Be careful here.** Now we need to authorize a new Org to deploy to. This is a little tricky since we don't have a web browser on on remote linux development machine. Easiest way is to use an Access Token, and you can do that from the Salesforce CLI on your **local machine**. Use the ```sfdx force:org:display command```, and use the Access Token in the resulting output (red line) below:
	
<img width="589" alt="Screen Shot 2022-02-09 at 11 55 33 am" src="https://user-images.githubusercontent.com/41508645/153101609-1ab7803c-8e34-471f-ae01-a6ac2e4fe1d4.png">

**Step 7:** From you Codespace Linux machine, use the following command from your terminal and enter the Access Token when prompted:

```sfdx auth:accesstoken:store --instanceurl https://MyVeryCoolOrg.my.salesforce.com/ ```

<img width="1052" alt="Screen Shot 2022-02-09 at 12 04 20 pm" src="https://user-images.githubusercontent.com/41508645/153102380-5def9aaa-9059-4132-9a2e-0e21ce2d3e83.png">

**Step 8:** Set your new autherized org in Visual Studio Code 

<img width="475" alt="Screen Shot 2022-02-09 at 12 52 22 pm" src="https://user-images.githubusercontent.com/41508645/153106958-52385109-82b4-47eb-a426-2d347db49feb.png">

