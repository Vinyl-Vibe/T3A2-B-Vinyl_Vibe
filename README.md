# Vinyl Vibe - T3A2-B

Intro/Banner image

**Frontend Repo Link:** https://github.com/Vinyl-Vibe/vinyl-vibe-frontend

**Backend Repo Link:** https://github.com/Vinyl-Vibe/vinyl-vibe-backend

<br>

## Table of Contents

-   [App Functionality]()
    -   [List]()
    -   [Meets client needs]()
    -   [Smooth UI/User Flow]()

<br>

-   [Testing]()
    -   [Manual (Dev & Prod)]()
    -   [Programmatic (Dev & Prod)]()

<br>

-   [Deployment]()
    -   [Client]()
    -   [Server (env var)]()
    -   [Database (local, prod)]()

<br>

-   [Maintainability & Scalability]()
    -   [Item]()

<br>

-   [Project Management (Trello)]()
    -   [Planning Methodology/intro]()
    -   [Team Members (Strength & Weaknesses for task assignments)]()
    -   [Trello breakdown - labels, difficulty level, git commit links)]()
    -   [Trello screenshots)]()

<br>

-   [Changes & Updates to Plan (Part-A)]()
    -   [Library Changes]()
    -   [Feature Changes)]()
    -   [Link to Original Plan Document (Part-A)]()

<br>

## Features and Functionality

The Vinyl Vibe Website has been designed to be the ideal digital presence for the Bricks and mortar, cult status record store of the same name in Regional NSW.

It features:

    * Landing Page
    * Admin Dashboard

    * Products section, separated into the categories:
        - Vinyl
        - Turntables
        - Accessories
        - Merchandise

    * Customer Login page
    * Shopping Cart
    * Order History
    * Stripe integration for Payments

*** 
## How it meets Client Needs

We determined the needs of the clients by establishing User Stories for the 4 main users of the Vinyl Vibe Website. We looked at demographic, goals, motivations, and frustrations to come up with the following statements:

### User 1
![User Story 1](docs/user-stories/user-story-short-1.png)

### Reflection 1
Norm's business now has a website that new customers feel comfortable purchasing from. They have a safe method of payment with Stripe integration. The modern branding is simple and unobtrusive, with just a touch of colour that draws the eye to the logo. The UI/UX is efficient and intuitive. He can now display his stock for sale in an efficient manner that has helped to improve sales. 

<br>

### User 2
![User Story 2](docs/user-stories/user-story-short-2.png)

### Reflection 2
Ruby has been extremely pleased with the Admin Dashboard. She can now track sales, orders, product lines, users, and abandoned carts. She can update the products for sale in a very straightforward way. More of the stock that was in the shop is now being advertised, which has led to increased sales, moving closer to her goal of growing the store to become a music destination for the world, rather than the best kept secret of only a few. The website has leant legitimacy to the business, so when previous customers are re-targeted for advertising, she knows that her conversion rate has improved. 

<br>

### User 3
![User Story 3](docs/user-stories/user-story-short-3.png)


### Reflection 3

Atticus is now able to keep up-to-date with what is in stock at Vinyl Vibe and can make regular orders from the convenience of his phone.  Now that there is an easy system to catalogue Norm's vast collection of hard to find Australian records, Atticus has been on a bit of a spending spree. Turns out Norm had many of the records that Atticus had been seeking for his collection for many years, sitting in milk crates out the back of his shop, unadvertised! Atticus has been able to expand his record collection quickly, with rare and hard to find records. He now regularly recommends Vinyl Vibe to his fellow audiophiles and music collectors. This has bought considerably more customers into the shop, which has meant a growth in sales and market share. 
<br>

### User 4
![User Story 4](docs/user-stories/user-story-short-4.png)

### Reflection 4

Diego has been extremely impressed with the Vinyl Vibe website. He no longer has to ring Norm at 3am (Seattle time) to see if he has particular records that his customers are looking for. He can just look on Norm's website. In an effort to improve their reciprocal business arrangement, Diego has now commissioned a website for his store, The Needle Drop, which will have all of the same functionality of the Vinyl Vibe site, but with his own branding on it. Now when he rings Norm, its just to reminisce about the good old days when they used to tour together as Roadies. 
 
<br>

*** 
## API Endpoints
This section provides detailed information about the available API endpoints, their usage, and expected responses.

<br>

### Auth Routes:

---


<br>
<br>

| FUNCTION | PATH | METHOD | AUTH REQUIRED | QUERY PARAMETERS |
|----------|------|--------|---------------|------------------|
| Register a new user | `/auth/register` | POST | null | null |

<br>

**Example Request Body**:
```json
{
  "email": "test101@example.com",
  "password": "password123"
}
```
**Example Success Response** (201 Created):
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9....",
  "user": {
    "id": "6766a7f3ef7cd743418164f8",
    "email": "test101@example.com",
    "role": "user"
  }
}
```

<br>

**Error Responses**:

- 400 Bad request:

```json
{
  "status": "fail",
  "error": {
    "statusCode": 400,
    "status": "fail",
    "isOperational": true
  },
  "message": "User already exists",
  "stack": {STACK_DATA}
}
```
```json
{
  "status": "fail",
  "error": {
    "statusCode": 400,
    "status": "fail",
    "isOperational": true
  },
  "message": "Email and password are required",
  "stack": {STACK_DATA}
}
```
<br>
<br>

---

<br>
<br>

| FUNCTION | PATH | METHOD | AUTH REQUIRED | QUERY PARAMETERS |
|----------|------|--------|----------------|------------------|
| User login | `/auth/login` | POST | JWT in header | null |

<br>

**Example Request Body**:
  ```json
  {
    "username": "damian@example",
    "password": "password123"
  }
  ```

<br>

**Example Success Response** (201 Created):
  ```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..........",
  "user": {
    "id": "675be0befe6e8441a443e11b",
    "email": "damian@example.com",
    "role": "admin"
    }
}
  ```

<br>

**Error Responses**:
  
  - 400 Bad Request:

```json
{
  "status": "fail",
  "error": {
    "statusCode": 401,
    "status": "fail",
    "isOperational": true
  },
  "message": "Invalid credentials",
  "stack": {STACK_DATA}
}
```

<br>

---

<br>
<br>

| FUNCTION | PATH | METHOD | AUTH REQUIRED | QUERY PARAMETERS |
|----------|------|--------|----------------|------------------|
| Get current users account | `/auth/me` | POST | JWT in header | null |

**Example Request Body**

Bearer Token inheritted 

<br>

**Example Success Response** (201 Created):
  ```json
{
  "user": {
    "id": "675be0befe6e8441a443e11b",
    "email": "damian@example.com",
    "role": "admin",
    "profile": {
      "address": {},
      "firstName": "Damian",
      "lastName": "Petrov"
    },
    "socialLogins": [],
    "createdAt": "2024-12-13T07:22:38.291Z",
    "updatedAt": "2024-12-19T12:50:48.145Z"
  }
}
  ```


### Cart Routes

---

<br>
<br>

| FUNCTION | PATH | METHOD | AUTH REQUIRED | QUERY PARAMETERS |
|----------|------|--------|----------------|------------------|
| Get current user's cart | `/carts/me` | GET | JWT in header | null |

**Example of successful response**
```json
{
  "status": "success",
  "cart": {
    "_id": "6766921332d3cebf4d98e813",
    "user": {
      "id": "675be0befe6e8441a443e11b",
      "email": "damian@example.com"
    },
    "products": [
      {
        "product": {
          "id": "675ad9b77d85749f98a8568c",
          "name": "Galactaphonic",
          "price": 39.99,
          "type": "vinyl",
          "thumbnail": ""
        },
        "quantity": 1
      }
    ],
    "createdAt": "2024-12-21T10:01:55.498Z",
    "updatedAt": "2024-12-21T10:01:55.498Z"
  }
}
```
<br>
<br>

---


<br>
<br>

| FUNCTION | PATH | METHOD | AUTH REQUIRED | QUERY PARAMETERS |
|----------|------|--------|----------------|------------------|
| Get all user's carts | `/carts` | GET | JWT in header | ADMIN |

<br>

**Example Success Response - 200 OK**

```json
{
  "status": "success",
  "carts": [
    {
      "_id": "6765647589fd56601033b9a4",
      "user": {
        "id": "676529c020b6a63cfbad0c6d",
        "email": "niaali@example.com"
      },
      "products": [
        {
          "product": {
            "id": "675aed497d85749f98a856c3",
            "name": "Audio-Technica AT618a Disc Stabilizer",
            "price": 59,
            "type": "accessory",
            "thumbnail": ""
          },
          "quantity": 2
        }
      ],
      "createdAt": "2024-12-20T12:35:01.581Z",
      "updatedAt": "2024-12-20T12:35:01.581Z"
    },
    {
      "_id": "676564a389fd56601033b9b3",
      "user": {
        "id": "67652a1920b6a63cfbad0ca3",
        "email": "barbaragarcia@example.com"
      },
      "products": [
        {
          "product": {
            "id": "676127e8303f21258a4e6685",
            "name": "Bottle Openner",
            "price": 5,
            "type": "merch"
          },
          "quantity": 1
        }
      ],
      "createdAt": "2024-12-20T12:35:47.977Z",
      "updatedAt": "2024-12-20T12:35:47.977Z"
    }
  ]
}
```
<br>
<br>

---


<br>
<br>

| FUNCTION | PATH | METHOD | AUTH REQUIRED | QUERY PARAMETERS |
|----------|------|--------|----------------|------------------|
| Add item to current users cart | `/carts` | POST | JWT in header | `productId`, `quantity` |

<br>

**Example Request Body**
```json
  {
      "productId": "675af09e7d85749f98a856cd",
      "quantity": 1
  }
```

**Example Success Response - 200 OK**

```json
{
  "status": "success",
  "cart": {
    "_id": "6766921332d3cebf4d98e813",
    "user": {
      "id": "675be0befe6e8441a443e11b",
      "email": "damian@example.com"
    },
    "products": [
      {
        "product": {
          "id": "675af09e7d85749f98a856cd",
          "name": "Ivy and the Big Apples",
          "price": 39.99,
          "type": "vinyl",
          "thumbnail": ""
        },
        "quantity": 1
      }
    ],
    "createdAt": "2024-12-21T10:01:55.498Z",
    "updatedAt": "2024-12-21T12:31:01.163Z"
  }
}
```

***
## Testing

***

## Deployment

***

## Maintainability and Scalability 

***

## Project Management

***

## Changes and Updates from Part A

***


    
