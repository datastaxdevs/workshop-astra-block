<!--- STARTEXCLUDE --->
# Workshops Astra Block!

<img src="img/badge.png?raw=true" width="150" align="right" />

[![Gitpod ready-to-code](https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod)](https://gitpod.io/#https://github.com/datastaxdevs/workshop-astra-block)
[![License Apache2](https://img.shields.io/hexpm/l/plug.svg)](http://www.apache.org/licenses/LICENSE-2.0)
[![Discord](https://img.shields.io/discord/685554030159593522)](https://discord.com/widget?id=685554030159593522&theme=dark)

> ⚠️ Difficulty: **`Intermediate`, we expect you to already know Javascript and TypeScript.**

Today we are building [THIS](https://eth-explorer.datastax.com/)

<img src="https://github.com/datastaxdevs/workshop-astra-block/blob/master/img/demo.png?raw=true">


## 📋 Table of content

[**HOUSEKEEPING**](#)
- [Objectives](#objectives)
- [Acknowledgements](#acknowledgements)
- [Frequently asked questions](#frequently-asked-questions)
- [Materials for the Session](#materials-for-the-session)

[**LAB1 - Database Initialization**](#1-database-initialization)
- [1.1 - Create Astra Account](#11---create-an-astra-account)
- [1.2 - Create Astra Token](#12---create-an-astra-token)
- [1.3 - Apply for Astra Block](#)

[**LAB2 - Astra Block Quick Start**](#)
- [2.1 - Request Access](#)
- [2.2 - Create Astra Block DB](#)
- [2.3 - First Requests](#)

[**LAB3 - Ethereum Explorer**](#)
- [3.1 - Setup the app](#)
- [3.2 - Start the app](#)

## HouseKeeping

### Objectives

* Discover how to use the following technologies: 
  * **Spring Data:** the Object Mapping layer of Spring
  * **Spring Data Cassandra:** what traps to avoid
  * **Spring Security:** how to handle authentication with OAuth2
  * **Spring MVC:** how to expose REST API and controllers
  * **Spring Webflux:** how to use the new `WebClient`
  * **Thymeleaf:** how to build a user interface with Spring
  * **Spring Test:** How to run tests
  * **Astra DB** (a Database-as-a-service built on Apache Cassandra)
* Han fun with an interactive session

### Acknowledgements

This application has been built based on the work of [**Java Brains**](https://www.youtube.com/channel/UCYt1sfh5464XaDBH0oH_o7Q), a famous youtuber *(500k+ subscribers)*. On his channel you can find the full [*Code with me Series*](https://www.youtube.com/watch?v=LxVGFBRpEFM), 16 episodes for building this application step-by-step. The link to each episode is provided at the end of this readme.

### Frequently asked questions

<p/>
<details>
<summary><b> 1️⃣ Can I run this workshop on my computer?</b></summary>
<hr>
<p>There is nothing preventing you from running the workshop on your own machine, If you do so, you will need the following
<ol>
<li><b>git</b> installed on your local system
<li><b>JDK 8+</b> installed on your local system
<li><b>Maven 3.6+</b> installed on your local system
</ol>
</p>
In this readme, we try to provide instructions for local development as well - but keep in mind that the main focus is development on Gitpod, hence <strong>We can't guarantee live support</strong> about local development in order to keep on track with the schedule. However, we will do our best to give you the info you need to succeed.
</details>
<p/>
<details>
<summary><b> 2️⃣ What other prerequisites are required?</b></summary>
<hr>
<ul>
<li>You will need an enough *real estate* on screen, we will ask you to open a few windows and it does not file mobiles (tablets should be OK)
<li>You will need a GitHub account eventually a google account for the Google Authentication (optional)
<li>You will need an Astra account: don't worry, we'll work through that in the following
<li>As Intermediate level we expect you to know what java and Spring are. 
</ul>
</p>
</details>
<p/>
<details>
<summary><b> 3️⃣ Do I need to pay for anything for this workshop?</b></summary>
<hr>
<b>No.</b> All tools and services we provide here are FREE. FREE not only during the session but also after.
</details>
<p/>
<details>
<summary><b> 4️⃣ Will I get a certificate if I attend this workshop?</b></summary>
<hr>
Attending the session is not enough. You need to complete the homeworks detailed below and you will get a nice badge that you can share on linkedin or anywhere else *(open api badge)*
</details>
<p/>

> [🏠 Back to Table of Contents](#-table-of-content)

### Materials for the Session

It doesn't matter if you join our workshop live or you prefer to work at your own pace,
we have you covered. In this repository, you'll find everything you need for this workshop:

- [Slide deck](/slides/slides.pdf)
- [Discord chat](https://dtsx.io/discord)
- [Questions and Answers](https://community.datastax.com/)
- [Twitch backup](https://www.twitch.tv/datastaxdevs)

----

## 1. Database Initialization

### 1.1 - Create an Astra Account

> **Note**: **Datastax Astra** is a cloud-native, fully managed database-as-a-service (DBaaS) based on Apache Cassandra. It provides a scalable, performant and highly available database solution without the operational overhead of managing Cassandra clusters. Astra supports both SQL and NoSQL APIs, and includes features like backup and restore, monitoring and alerting, and access control. It enables developers to focus on application development while the database infrastructure is managed by Datastax.

- `✅ 1.1.a` - Access [https://astra.datastax.com](https://astra.datastax.com) and register with `Google` or `Github` account

![](https://github.com/DataStax-Academy/cassandra-for-data-engineers/blob/main/images/setup-astra-1.png?raw=true)

### 1.2 - Create an Astra Token

- `✅ 1.2.a` Locate `Settings` (#1) in the menu on the left, then `Token Management` (#2) 

- `✅ 1.2.b`Select the role `Organization Administrator` before clicking `[Generate Token]`

![](https://github.com/DataStax-Academy/cassandra-for-data-engineers/blob/main/images/setup-astra-2.png?raw=true)

- `✅ 1.2.c` - Copy your token in the clipboard. With this token we will now create what is needed for the training.

![](https://github.com/DataStax-Academy/cassandra-for-data-engineers/blob/main/images/setup-astra-3.png?raw=true)