---
layout: post
title: How To Setup A PostgreSQL DB Instance with Shopify Data
---

At Enquire, we use Postgres as our core database and for anyone who’s spent years in excel… it’s a dream. After a few searches, I realized there was no central resource/how-to for e-commerce analysis in Postgres, especially for Shopify. With Heroku’s database-as-a-service, setting up a Postgres database takes less than a minute and connecting to your Shopify data takes another (thanks to StitchData).

For any non-engineer who’s wanted to dive into SQL or Postgres this overview should help. I’ve also included a few queries you can copy and paste to get your started.

If you don’t already, you’ll need to create accounts with the below:
* Shopify
* Heroku
* StitchData

You’ll also need a Postgres client. I’m a big fan of Postico for Mac. The free version is more than enough to get you started. (Any recommendations for PC client? Let me know and I’ll update here)

## Shopify
Hopefully you already have a Shopify account with order data. If not, you can use the Simple Sample Data Shopify app to populate with mock data (h/t @stuart_abc.)

## Heroku
Create a Heroku account if you don’t already have one (you can select any language in the on-boarding flow). After you’ve created an account, you’ll be presented with the “Create New App” screen–simply follow the prompts to create an app. Once you’re app is created click “Resources” and in the “Add-Ons” search for “Postgres”. Heroku’s free plan unfortunately doesn’t offer enough rows to fully extract your Shopify instance, so you’ll need to select Hobby Basic ($9/month).

![Heroku Screenshot](assets/heroku-screenshot.png){: .center-image }

After you’ve Provisioned your db, select Heroku Postgres in your add-ons list to open your db dashboard. Select “Settings” and click “View Credentials”. You’ll need these in the steps below.

![Heroku database](assets/heroku-database.png){: .center-image }

## StitchData
Create a StitchData account here and follow the steps to setup your free account. Unless you’re Shopify store is doing considerable volume (100k+ customers), their free version should be enough to get your started.

Once you’ve connected your Shopify account, select Postgres DB as your destination. To connect your newly created database, simple follow the steps prompted to you and enter your host, database name, username, pw. You can leave the encryption type to None.

After you’ve completed these steps, StitchData will begin extracting your Shopify data and loading it into your Postgres DB. This process should take 30 minutes to an hour. In the interim, you can install Postico and insert your DB credentials.

To do this, simply input your Heroku database credentials after clicking “New Favorite”.


![Postico](assets/postico-setup.png){: .center-image }

## Querying Your Shopify Data
Once StitchData is done syncing and your DB credentials are entered in Postico, you can start querying your data.




