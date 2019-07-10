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

Shopify
Hopefully you already have a Shopify account with order data. If not, you can use the Simple Sample Data Shopify app to populate with mock data (h/t @stuart_abc.)

Heroku
Create a Heroku account if you don’t already have one (you can select any language in the on-boarding flow). After you’ve created an account, you’ll be presented with the “Create New App” screen–simply follow the prompts to create an app. Once you’re app is created click “Resources” and in the “Add-Ons” search for “Postgres”. Heroku’s free plan unfortunately doesn’t offer enough rows to fully extract your Shopify instance, so you’ll need to select Hobby Basic ($9/month).

![Heroku Screenshot](assets/heroku-screenshot.png){: .center-image }
