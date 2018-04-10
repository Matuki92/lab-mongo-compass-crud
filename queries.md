![Ironhack Logo](https://i.imgur.com/1QgrNNw.png)

# Answers

## 1. Find all the companies that include 'Facebook' on the **name** field.

 - **`query`**: {name: 'Facebook'}
 
 ## 2. Find all the companies which **category_code** is 'web'. Retrive only their `name` field:

 - **`query`**: {category_code: 'web'}
 - **`projection`**: {name: 1, _id: 0}

## 3. Find all the companies named "Twitter", and retrieve only their `name`, `category_code` and `founded_year` fields.

## 4. Find all the companies who have `web` as their **category_code**, but limit the search to 50 companies.

    > db.companies.find({category_code: "web"},{name: 1, _id: 0}).limit(50)
{ "name" : "TechnologyGuide" }
{ "name" : "Wetpaint" }
{ "name" : "Postini" }
{ "name" : "Geni" }
{ "name" : "Fox Interactive Media" }
{ "name" : "Gizmoz" }
{ "name" : "StumbleUpon" }
{ "name" : "eBay" }
{ "name" : "Viacom" }
{ "name" : "Plaxo" }
{ "name" : "Yahoo!" }
{ "name" : "Mahalo" }
{ "name" : "CriticalMetrics" }
{ "name" : "Gannett" }
{ "name" : "Thoof" }
{ "name" : "Info" }
{ "name" : "JotSpot" }
{ "name" : "Meetup" }
{ "name" : "Mercora" }
{ "name" : "NetRatings" }

## 5. Find all the companies which **category_code** is 'enterprise' and have been founded in 2005. Retrieve only the `name`, `category_code` and `founded_year` fields.

    > db.companies.find({category_code: "enterprise"},{name: 1, category_code: 1, founded_year: 1 , _id: 0})
{ "name" : "AdventNet", "category_code" : "enterprise", "founded_year" : 1996 }
{ "name" : "Mashery", "category_code" : "enterprise", "founded_year" : 2006 }
{ "name" : "KickApps", "category_code" : "enterprise", "founded_year" : 2004 }
{ "name" : "ConVerdge", "category_code" : "enterprise", "founded_year" : 2006 }
{ "name" : "PBworks", "category_code" : "enterprise", "founded_year" : 2005 }
{ "name" : "Socialtext", "category_code" : "enterprise", "founded_year" : 2002 }
{ "name" : "NetSuite", "category_code" : "enterprise", "founded_year" : 1998 }
{ "name" : "LongJump", "category_code" : "enterprise", "founded_year" : 1999 }
{ "name" : "Brightcove", "category_code" : "enterprise", "founded_year" : 2004 }
{ "name" : "Nirvanix", "category_code" : "enterprise", "founded_year" : 2007 }
{ "name" : "Userplane", "category_code" : "enterprise", "founded_year" : 2001 }
{ "name" : "Scrybe", "category_code" : "enterprise", "founded_year" : 2007 }
{ "name" : "Echo", "category_code" : "enterprise", "founded_year" : 2007 }
{ "name" : "MindTouch", "category_code" : "enterprise", "founded_year" : 2004 }
{ "name" : "Akamai Technologies", "category_code" : "enterprise", "founded_year" : 1998 }
{ "name" : "Six Apart", "category_code" : "enterprise", "founded_year" : 2001 }
{ "name" : "Cloudant", "category_code" : "enterprise", "founded_year" : 2008 }
{ "name" : "KIT digital", "category_code" : "enterprise", "founded_year" : 2008 }
{ "name" : "Sun Microsystems", "category_code" : "enterprise", "founded_year" : 1982 }
{ "name" : "NewsGator", "category_code" : "enterprise", "founded_year" : 2004 }


## 6. Find all the companies that have been **founded** on the 2000 or have 20 **employees**. Sort them descendingly by their `number_of_employees`.

    > db.companies.find( { $or: [ { founded_year: 2000 },{ number_of_employees: 20 } ] },{ number_of_employees: 1, _id: 0 } )
{ "number_of_employees" : null }
{ "number_of_employees" : null }
{ "number_of_employees" : null }
{ "number_of_employees" : 20 }
{ "number_of_employees" : 20 }
{ "number_of_employees" : 600 }
{ "number_of_employees" : 20 }
{ "number_of_employees" : 20 }
{ "number_of_employees" : 20 }
{ "number_of_employees" : 16 }
{ "number_of_employees" : 20 }
{ "number_of_employees" : 20 }
{ "number_of_employees" : null }
{ "number_of_employees" : 55 }
{ "number_of_employees" : 20 }
{ "number_of_employees" : null }
{ "number_of_employees" : 800 }
{ "number_of_employees" : null }
{ "number_of_employees" : 250 }
{ "number_of_employees" : 180 }


## 7. Find all the companies that do not include `web` nor `social` on their **category_code**. Limit the search to 20 documents and retrieve only their `name` and `category_code`.

    > db.companies.find( { $nor: [ {category_code: "web"}, {category_code: "social"} ] },{ name: 1, category_code: 1, _id: 0 } ).limit(20)
{ "name" : "AdventNet", "category_code" : "enterprise" }
{ "name" : "Snimmer", "category_code" : null }
{ "name" : "Zoho", "category_code" : "software" }
{ "name" : "Digg", "category_code" : "news" }
{ "name" : "Omnidrive", "category_code" : "network_hosting" }
{ "name" : "Flektor", "category_code" : "games_video" }
{ "name" : "Helio", "category_code" : "mobile" }
{ "name" : "AllofMP3", "category_code" : "games_video" }
{ "name" : "Drigg", "category_code" : null }
{ "name" : "Scribd", "category_code" : "news" }
{ "name" : "Slacker", "category_code" : "music" }
{ "name" : "Lala", "category_code" : "games_video" }
{ "name" : "Joost", "category_code" : "games_video" }
{ "name" : "CBS", "category_code" : "news" }
{ "name" : "Babelgum", "category_code" : "games_video" }
{ "name" : "Cisco", "category_code" : "network_hosting" }
{ "name" : "Powerset", "category_code" : "search" }
{ "name" : "Technorati", "category_code" : "advertising" }
{ "name" : "SpinVox", "category_code" : "messaging" }
{ "name" : "AddThis", "category_code" : "advertising" }


## 8. Find all the companies that were not **founded** on 'June'. Skip the first 50 results and retrieve only the `founded_month` and `name` fields.

    > db.companies.find( { founded_month: { $ne: 'June' } }, {name: 1, founded_month: 1, _id: 0} ).skip(50)
{ "name" : "Wesabe", "founded_month" : 12 }
{ "name" : "Jangl SMS", "founded_month" : 3 }
{ "name" : "SmugMug", "founded_month" : 11 }
{ "name" : "Prosper", "founded_month" : 2 }
{ "name" : "Google", "founded_month" : 9 }
{ "name" : "Jajah", "founded_month" : 1 }
{ "name" : "Skype", "founded_month" : 8 }
{ "name" : "YouTube", "founded_month" : 2 }
{ "name" : "Stickam", "founded_month" : 2 }
{ "name" : "blogTV", "founded_month" : 5 }
{ "name" : "Livestream", "founded_month" : 5 }
{ "name" : "Ustream", "founded_month" : null }
{ "name" : "AdaptiveBlue", "founded_month" : null }
{ "name" : "Pando Networks", "founded_month" : 7 }
{ "name" : "Intel", "founded_month" : null }
{ "name" : "GrandCentral", "founded_month" : 4 }
{ "name" : "Ikan", "founded_month" : 12 }
{ "name" : "delicious", "founded_month" : 9 }
{ "name" : "Topix", "founded_month" : 6 }
{ "name" : "Jobster", "founded_month" : 1 }


## 9. Find all the companies that have 50 employees, but do not correspond to the 'web' **category_code**. 

    > db.companies.find( { $and: [ { number_of_employees: 50 } , { category_code: { $ne: "web" } } ] } , {name: 1, _id: 0})
{ "name" : "Scribd" }
{ "name" : "adBrite" }
{ "name" : "Socialtext" }
{ "name" : "ONEsite" }
{ "name" : "boo-box" }
{ "name" : "Echo" }
{ "name" : "Six Apart" }
{ "name" : "OMGPOP" }
{ "name" : "Crunchyroll" }
{ "name" : "4INFO" }
{ "name" : "Jive Software" }
{ "name" : "BitGravity" }
{ "name" : "Peer39" }
{ "name" : "Lijit Networks" }
{ "name" : "ChoiceStream" }
{ "name" : "IceBreaker" }
{ "name" : "Central Desktop" }
{ "name" : "EASEUS" }
{ "name" : "Wrike" }
{ "name" : "Athena Archiver" }
Type "it" for more


## 10. Find all the companies that have been founded on the 1st of the month, but does not have either 50 employees nor 'web' as their **category_code**. Retrieve only the `founded_day` and `name` and limit the search to 5 documents.

## 11. Find all the companies which the `price_amount` of the `acquisition` was **`40.000.000`**. Sort them by `name`.

## 12. Find all the companies that have been acquired on January of 2014. Retrieve only the `acquisition` and `name` fields.
