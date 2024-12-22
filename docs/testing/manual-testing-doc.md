## Manual Testing Documentation

### Project Name

Vinyl Vibe App

---

### Test Details

- **Environment**:
  - OS: `Windows 11`
  - Browser: `Google Chrome v119`
  - Database: `MongoDB Atlas`
- **Date**: 2024-12-13

---

### Personas & Testers

#### Persona: New Vinyl Collector

- **Description**: Beginner collector, tech-savvy but unfamiliar with niche vinyl platforms.
- **Goals**: Build their collection, explore curated vinyl recommendations.
- **Pain Points**: Limited knowledge of grading systems, prefers visual browsing.
- **Test User**:
  - Age: 26
  - Location: Melbourne, Australia
  - Skill Level: Beginner
  - Notes: Has purchased vinyl from general e-commerce sites but is new to specialty apps.

---

### Test Scenarios

#### 1. Browsing and Searching for Vinyl

- **Persona**: New Vinyl Collector
- **Test Steps**:
  1. Navigate to the homepage.
  2. Use filters to search for "rock" genre records.
  3. Add a record to the cart.
- **Expected Result**:
  - Filters should display relevant options clearly.
  - User should easily add a record to the cart.
- **Actual Result**:
  - User found filters confusing and struggled to find the "Add to Cart" button.
- **Feedback**:
  - "The filters feel overwhelming, and I wasn't sure where to start."
- **Status**: ❌ _Failed_
- **Notes**: Simplify filter options and add tooltips for clarity.

#### 2. Navigating Vinyl Grading Information

- **Persona**: New Vinyl Collector
- **Test Steps**:
  1. View a product's details page.
  2. Read the vinyl grading information.
- **Expected Result**:
  - Grading info should be accessible and easy to understand.
- **Actual Result**:
  - User found the grading system too technical.
- **Feedback**:
  - "I wish there was a simpler explanation or examples."
- **Status**: ⚠️ _Partially Passed_
- **Notes**: Consider a grading guide or simplified terms.

--- 

#### 3. New user - browsing to checkout

**email:** user@example.com
<br>
**password:** password123
<br>
**Role:** User

- **Persona**: New standard user
- **Test Steps**:
  1. Navigate to the homepage.
  2. Browse Products via Vinyl, Turn tables, Accessories or Merchandise.
  3. Add product/s to the cart.
  4. Update product Qty's via cart options menu (located at shopping cart top right)
  5. Test delete product from cart.
  6. Checkout with existing products in cart.
  7. Enter shipping information.
  8. Payment testing with FAKE card details below:
    - Successful payment:
      - Card Number: 4242 4242 4242 4242 | EXP: 12/26 | CCV: 123
    - Insucifient funds:
      - Card Number: 4000 0000 0000 9995 | EXP: 12/26 | CCV: 123
  9. Order confirmation page
  10. View orders
  11. Secect which order to view
  12. Continue shopping
  13. Logout

- **Expected Result**:
  - Standard user to be able to add products to cart and purchase products via stripe.
  - User able to edit products in cart to suite changing needs.
  - User able to view order history and check date/status/products in by order ID
- **Actual Result**:
  - User was able to add products to cart and purchase through the stripe gateway (using a fake card for stripe transactions).
  - Cart update and remove options worked as expected.
  - Viewing order history and contents worked as expected.
- **Feedback**:
  - Everything works as expected, could use some extra features like a back button on individual product pages
  - 
- **Status**: Passed
- **Notes**: Can add back button feature to individual product page. 

---

#### 4. Admin testing - Admin dashboard

**email:** admin@example.com
<br>
**password:** password123
<br>
**Role:** Admin

- **Persona**: Admin user
- **Test Steps**:
  1. Navigate to the homepage.
  2. 
  3. 
- **Expected Result**:
  - F
  - U
- **Actual Result**:
  - 
- **Feedback**:
  - 
- **Status**: 
- **Notes**: 

### Summary

| **Test Scenario**      | **Persona**         | **Status**          | **Notes**                        |
| ---------------------- | ------------------- | ------------------- | -------------------------------- |
| Browsing and Searching | New Vinyl Collector | ❌ Failed           | Filters and UI need improvement. |
| Grading Information    | New Vinyl Collector | ⚠️ Partially Passed | Add a grading guide or examples. |

---

### Recommendations

- Redesign filter options for simplicity and clarity.
- Add a visual grading guide to product pages.
- Conduct additional tests with experienced collectors for comparison.
