<!--- STARTEXCLUDE --->
# Workshops Astra Block!

<img src="img/badge.png?raw=true" width="150" align="right" />

[![Gitpod ready-to-code](https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod)](https://gitpod.io/#https://github.com/datastaxdevs/workshop-astra-block)
[![License Apache2](https://img.shields.io/hexpm/l/plug.svg)](http://www.apache.org/licenses/LICENSE-2.0)
[![Discord](https://img.shields.io/discord/685554030159593522)](https://discord.com/widget?id=685554030159593522&theme=dark)

> ⚠️ Difficulty: **`Intermediate`, we expect you to already know Javascript and TypeScript.**

Today we are building [THIS](https://eth-explorer.datastax.com/)

<img src="https://github.com/datastaxdevs/workshop-astra-block/blob/main/img/demo.png?raw=true" >

> **Info**: [Documentation of the product used today](https://docs.datastax.com/en/astra-serverless/docs/block/overview.html
)

## 📋 Table of content

<img src="https://github.com/datastaxdevs/workshop-astra-block/blob/main/img/menu.png?raw=true" align="right" width="250px"/>

[**HOUSEKEEPING**](#)
- [Objectives](#objectives)
- [Frequently asked questions](#frequently-asked-questions)
- [Materials for the Session](#materials-for-the-session)

[**LAB1 - Database Initialization**](#1-database-initialization)
- [1.1 - Create Astra Account](#11---create-an-astra-account)
- [1.2 - Create Astra Token (optional)](#12---create-an-astra-token)

[**LAB2 - Astra Block Quick Start**](#2---astra-block-quick-start)
- [2.1 - Request Access](#21---request-access)
- [2.2 - Create Astra Block DB (optional)](#22---create-astra-block-db)
- [2.3 - First Requests with Cql Console (optional)](#23---first-requests-with-cql-console)
- [2.4 - Open Astra GraphQL](#24---open-astra-graphql)
- [2.5 - Open Free GraphQL](#25---open-free-graphql)
- [2.6 - GraphQL queries](#26---graphql-queries)

[**LAB3 - Ethereum Explorer**](#lab3---ethereum-explorer)
- [3.1 - Setup the app](#31---setup-the-app)
- [3.2 - Start the app](#32---start-the-app)
- [3.3 - Deployment to Vercel](#33---deploy-to-vercel)

## HouseKeeping

### Objectives

* Give you an first understanding about Blockchain and Web3.
* Present the limitations of blockchains for realtime applications and how off-loading can help.
* Discover NoSQL dsitributed databases and specially Apache Cassandra™.
* Show a sample usage of the GraphQL API provided by Stargate on top of Cassandra.
* Introduce AstraDB and Astra Block.

### Frequently asked questions

<p/>
<details>
<summary><b> 1️⃣ Can I run this workshop on my computer?</b></summary>
<hr>
<p>There is nothing preventing you from running the workshop on your own machine, If you do so, you will need the following
<ol>
<li><b>git</b> installed on your local system
<li><b>Javascript</b> installed on your local system
<li><b>Npm, Typescript</b> installed on your local system
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
<li>As Intermediate level we expect you to know what javascript, typescript and Next JS are. 
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

----

## 1. Database Initialization

### 1.1 - Create an Astra Account

> **Note**: **Datastax Astra** is a cloud-native, fully managed database-as-a-service (DBaaS) based on Apache Cassandra. It provides a scalable, performant and highly available database solution without the operational overhead of managing Cassandra clusters. Astra supports both SQL and NoSQL APIs, and includes features like backup and restore, monitoring and alerting, and access control. It enables developers to focus on application development while the database infrastructure is managed by Datastax.

- `✅ 1.1.a` - Access [https://astra.datastax.com](https://astra.dev/yt-03-08) and register with `Google` or `Github` account

![](img/astra-login.png?raw=true")

### 1.2 - Create an Astra Token

```diff
- ⚠️ NOT MANDATORY DURING THE LIVE WORKSHOP
```

- `✅ 1.2.a` Locate `Settings` (#1) in the menu on the left, then `Token Management` (#2) 

- `✅ 1.2.b`Select the role `Organization Administrator` before clicking `[Generate Token]`

![](https://github.com/DataStax-Academy/cassandra-for-data-engineers/blob/main/images/setup-astra-2.png?raw=true)

- `✅ 1.2.c` - Copy your token in the clipboard. With this token we will now create what is needed for the training.

![](https://github.com/DataStax-Academy/cassandra-for-data-engineers/blob/main/images/setup-astra-3.png?raw=true)


## 2. - Astra Block Quick Start

Astra Block is a blockchain data service that offers real-time indexed blockchain data for building Web3 and decentralized applications (dapps).

With Astra Block, you can stream a sanitized blockchain dataset into an Astra database in real-time. The second a new block is mined, your Astra database will immediately be updated with the new, clean blockchain data.

> `More Information:`
> - [Reference Documentation](https://docs.datastax.com/en/astra-serverless/docs/block/overview.html)
> - [QuickStart Page](https://docs.datastax.com/en/astra-serverless/docs/block/quickstart.html)

### 2.1 - Request Access

- `✅ 2.1.a` - Access the [registration page](https://www.datastax.com/products/astra-block) and select the `[REQUEST ACCESS]` button.

![](img/astra-block-request-1.png?raw=true")

- `✅ 2.1.b` - Fill the form with your contact information, make sure to use the email you used to register to Astra.

![](img/astra-block-request.png?raw=true")

- `✅ 2.1.c` - Wait for the team to enable you. It is a manual operation that can a bit of time.

![](img/astra-block-request-2.png?raw=true")

Upon submission, DataStax will begin reviewing your request. Once your request is approved, a DataStax representative will reach out to you via email to discuss the next steps for creating your Block-enabled database.

### 2.2 - Create Astra Block DB

```diff
- ⚠️ NOT EXECUTED DURING THE LIVE WORKSHOP
```

At this time, Block-enabled databases can only be manually created by DataStax upon request.

If you have yet to create your first Block-enabled database, you can request one by following the procedure in Request access to Astra Block.

If you’re already a user of Astra Block and would like to create additional Block-enabled databases, please send a request in a reply to your original Astra Block invitation email, or as a message via the Intercom widget in the lower right-hand corner of the Astra Portal.

- `✅ 2.2.a` - Locate button [Clone Bockchain Database] to start your journey.

![](img/astra-home.png?raw=true")

- `✅ 2.2.b` - Fill DB creation form selecting `Ethereum (Complete Dataset)`

![](img/astra-create.png?raw=true")


- `✅ 2.2.c` - It will take a few seconds for the database to be available

![](img/astra-initializing.png?raw=true")

- `✅ 2.2.d` - A new Tab will be available `Block`, make sure to `[Enable Block]`

![](img/astra-block-request-3.png?raw=true")

### 2.3 - First Requests with CQL CONSOLE

```diff
- ⚠️ NOT EXECUTED DURING THE LIVE WORKSHOP
```

- `✅ 2.3.a` - Locate tab `CQL Console` and show the console.


![](img/cql-console.png?raw=true")

- `✅ 2.3.b` - Pick the `ethereum` keyspace with CQLSH

```sql
use ethereum;
```

- `✅ 2.3.c` - Describe tables with CQLSH

```sql
describe table tokens;
```

- `✅ 2.3.d` - Access Table data

```sql
select address,decimals,name,symbol,block_timestamp 
from tokens 
LIMIT 10;
```

> `Output`
> ```
>  address                                    | decimals | name            | symbol | block_timestamp
> --------------------------------------------+----------+-----------------+--------+---------------------------------
>  0xc14ca0805194dc4a1319dcad80352d8033763b92 |       18 |             WJL |    WJL | 2018-12-25 08:24:03.000000+0000
>  0x69a2bf7c7fe7cd4ce69b8d645980261582e26e16 |        0 |  Artem Anisimov |     AA | 2019-12-30 14:19:51.000000+0000
>  0xca3537f73cce6dc0aa1611d79f4b0fdc2dfe31d2 |     null |                 |   null | 2017-02-06 18:28:26.000000+0000
>  0x17c5134461f501b4c00ac8082d2d5a3ff0ba2d3e |       18 |          YUANZE | YUANZE | 2021-06-11 12:24:53.000000+0000
>  0x62397c4e8f064a94806abcfc85fb96daf2d43e2c |        0 |                 |        | 2021-07-09 08:47:43.000000+0000
>  0x69510449d500fcaf8eb79a2f1448019f3854344a |        5 |        SD Chain |     SD | 2020-04-10 12:19:23.000000+0000
>  0xcbbd061680091d4d84db4db7a8060708d50f5e65 |       18 |          CoinUs |   BNUS | 2019-03-07 10:13:06.000000+0000
>  0x5da482344df827dccecd7c8aee675c463b12a915 |       18 |    FortFC Token |   FFCT | 2018-09-17 12:42:52.000000+0000
>  0x2c1bae1aec1bcc328da0cabea8c6a73c076f0af9 |       10 | NothingButBased |  BASED | 2022-10-12 17:33:47.000000+0000
>  0x99bada568a90e203374ee8ca2d938c1a319d4130 |       18 |             XXH |    XXH | 2018-11-17 06:34:56.000000+0000
> ```

### 2.4 - Open Astra GraphQL

```diff
- ⚠️ NOT EXECUTED DURING THE LIVE WORKSHOP
```

The application will use the GraphQL Api to interact with the database, let us have a look at this API.

- `✅ 2.4.a` - Locate Playground, in the `Connect` Tab by scrolling down and clicking graphQL

![](img/astra-graphql-1.png?raw=true")

- `✅ 2.4.b` - There click on the `GraphQL Playground` link.

![](img/astra-graphql-2.png?raw=true")

- `✅ 2.4.c` - List Keyspaces in db `workshop`

In the left part of the screen enter the following request and validate with the Big triangle button in the middle (play)

```yaml
query getAllKeyspaces{ 
  keyspaces {
    name 
  } 
}
```

> `Output`
> ![](img/gql-list-keyspaces.png?raw=true")

### 2.5 - Open Free GraphQL

```diff
+ ⚠️ EXECUTED DURING THE LIVE WORKSHOP
```

- `✅ 2.5.a` - Open the free GraphQL playground available at [https://graphql-demo.mead.io](https://graphql-demo.mead.io/)


- `✅ 2.5.b` - Change the URL to point to the database update for your

```
https://4ac96264-a997-47ee-9cad-c97ba836bc6f-us-west-2.apps.astra.datastax.com/api/graphql-schema
```

- `✅ 2.5.c` - Click on HTTP HEADER and populate

```json
{
  "x-cassandra-token": "AstraCS:NTUZWFSHzJFPbNSfHEsiWgoN:8117739d5965d24f0bf23951857a97338d3b049b0761d5bce5cbe6e2e36b2944"
}
```

> This token will be valid only today. It serves the purpose and making you testing with real data but after that you will have to create your won token, your own database.

### 2.6 - GraphQL queries

- `✅ 2.6.a` - Display documentation by click on the `DOCS` panel totally on the right of the playground.

![](img/gql-documentation.png?raw=true")


- `✅ 2.6.b` - Display the table list of the keyspace `ethereum`

```yaml
query getEthereumKeyspaceTables {
  keyspace(name:"ethereum") {
    name
    tables {
      name
      columns {
        name
        kind
        type {
          basic
          info {
            name
          }
        }
      }
    } 
  }
}
```

- `✅ 2.6.b` - Open a new  TAB and call it `DATA` and provide a new URL

```
https://4ac96264-a997-47ee-9cad-c97ba836bc6f-us-west-2.apps.astra.datastax.com/api/graphql/ethereum
```

![](img/astra-graphql-3.png?raw=true")


- `✅ 2.6.c` - Upload the header if needed with 

```json
{
  "x-cassandra-token": "AstraCS:NTUZWFSHzJFPbNSfHEsiWgoN:8117739d5965d24f0bf23951857a97338d3b049b0761d5bce5cbe6e2e36b2944"
}
```

- `✅ 2.6.d` - List content of table `tokens`, 

```yaml
query getTokenByAddress {
  tokens(value:{address:"0xc14ca0805194dc4a1319dcad80352d8033763b92"}) {
    values {
      address
      block_number
      block_timestamp
      decimals
      symbol
    }
  }
}
```

> `Output`
> ![](img/gql-gettokens.png?raw=true")
> ```yaml
> {
>   "data": {
>     "tokens": {
>       "values": [
>         {
>           "address": "0xc14ca0805194dc4a1319dcad80352d8033763b92",
>           "block_number": "6949212",
>           "block_timestamp": "2018-12-25T08:24:03.000Z",
>           "decimals": 18,
>           "symbol": "WJL"
>         }
>       ]
>     }
>   }
> }
> ```

## LAB3 - Ethereum Explorer

### 3.1 - Setup the app

- `✅ 3.1.a` ↗️ _Right Click and select open as a new Tab..._

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/datastaxdevs/workshop-astra-block)

- `✅ 3.1.b` Install dependencies. Wait for the environment to start and install dependencies with

```
yean install
```

### 3.2 - Start the app

- `✅ 3.2.a` Start the app with 

```
yarn start 
```

> **note**: if you want to run the app in production mode) or yarn dev for hot reloading


```
gp url 3000
```

### 3.3 - Deploy to Vercel

## Deployment
Deploy the app to Vercel using the button below:

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fdatastax%2Fblock-explorer&env=API_ACCESS_TOKEN,NEXT_PUBLIC_GRAPHQL_ENDPOINT&envDescription=Astra%20API%20keys%20needed%20for%20the%20application&project-name=Astra%20Block%20Explorer)
