# Learn MongoDB

## Why Learn MongoDB

Learning MongoDB can enhance your skill set as a tech professional, open up career opportunities, and equip you with the tools to work with modern data models and scalable databases effectively. Here are a few additional reasons to consider learning MongoDB.

 **Industry Demand:** MongoDB is widely used in tech companies, making it valuable to learn for better job prospects.

**NoSQL and Flexibility:** MongoDB's NoSQL and document-oriented approach enable handling diverse data scenarios and offer a different perspective than relational databases.

**Scalability and Performance:** MongoDB scales horizontally, handles large data volumes, and high traffic loads efficiently.

**Developer-Friendly:** MongoDB's user-friendly query language simplifies interaction with the database and streamlines development.

**Integration with Modern Tech Stack:** MongoDB integrates well with popular tech stacks, frameworks, and cloud platforms.

## How to Learn MongoDB

There are many ways to start learning MongoDB. MongoDB provides official documentation as well as MongoDB University to help new and experienced users learn and hone their skills, both free and highly recommended resources.

[MongoDB Official Documentation](https://www.mongodb.com/docs/)

[MongoDB University](https://learn.mongodb.com/)

# MongoDB Primer

If you want to quickly get started or simply understand how MongoDB works, this primer is perfect for you.

At the time of writing this (July 10th 2023) I am using the following versions:

| Software | Version |
| --------- | -------|
| MongoDB | 6.0.6 (API Version 1) |
| Mongosh | 1.10.1 |
| MongoDB Compass | 1.38.2 |

## Create a Free Account

We will be using MongoDB Atlas for this primer. MongoDB Atlas is a managed cloud database service that allows you to easily deploy, scale, and manage MongoDB databases without worrying about infrastructure setup or maintenance.

Create a free account [here](https://www.mongodb.com/cloud/atlas/register)

## Deploy Database 

After you confirm your email and sign in you will see the Deploy your database screen. 

![](assets/images/deploy.png)

Choose the free M0 option and select the provider that has a region closest to your location. 

## Security Setup

On the next screen you will have some options to secure your account. 

![](assets/images/security.png)

I used the following options for this guide:

**Authenticate Connection:** Username and Password

**Connect from:** My Local Environment

You will also need to add your IP address to the access list by choosing "Add My Current IP Address."

Save and continue to the Atlas main page.

## Load Sample Data

We will use the sample data that MongoDB provides for the following exercises. You might see an option to load sample data like this one:

![](assets/images/sample%201.png) 

If you don't see the option to load sample data at the top you can do so by selecting the more options icon (...) and then selecting "Load Sample Dataset" like this:

![](assets/images/sample%202.png)

Confirm that you are about to load the sample data and wait for the following message to confirm it has been loaded:

![](assets/images/loaded.png)

<!-- Break this into separate sections-->

## Installing mongosh

Next you need to install `mongosh` the process varies depending on your local operating system. Follow the download and install instructions for your system [here](https://www.mongodb.com/docs/mongodb-shell/install/)

Once you have `mongosh` installed you are ready to connect. 

## Connecting via Shell

Click the "Connect" button in Atlas:

![](assets/images/connect%200.png)

This will bring up the menu to choose the type of connection, select "Shell" :

![](assets/images/connect%201.png)

Since you already have MongoDB Shell installed choose that option and then copy/paste the connection string into your terminal.

>**Note** Remember to replace `<username>` with the username you created when you deployed the cluster.

![](assets/images/connect%202.png)

Enter your password for that user and press enter. You should see something like this when you are connected:

![](assets/images/connected.png)

You are now connected via mongosh!

## Basic Navigation

To show all of the databases run the following command:

`show dbs`

<details><summary>See output</summary>

![Alt text](assets/images/show.png)

</details>

Let's use the `sample_restaurants` database for our first practice exercise. 

Switch to the `sample_restaurants` database by using the `use` command:

`use sample_restaurants`

> **Note** If a database dose not exist the `use` command will create it. To avoid misspelling use tab complete. 

You should see a confirmation message that you've switched to the sample_restaurants database.

Now that you are in the sample_restaurants database, run the show command but for collections:

`show collections`

You should see the neighborhoods and restaurants collections. Let's focus on the restaurants collection first. 

To see how many documents are in the restaurants collection we'll use the `countDocuments` function. 





Run the following command to see how many there are and compare your answer to the one below:

`db.restaurants.countDocuments()`

<details><summary>See answer</summary>

25359

</details>