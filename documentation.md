# ============================================

## EXAMPLE DOCUMENTATION

### Ask for the Home Page

#### Step 1

Predicted Request components:

- Method: GET
- URL: /
- Headers: none
- Body: none

Predicted Response components:

- Status Code: 200
- Headers:
  - Content-Type: text/html
- Body: HTML page with navigation links to other pages

#### Step 2

In your browser open the chrome dev tools, navigate to [http://localhost:5000] and make a GET request for the Home Page (type "/" into the URL after 5000 and hit "enter").
Explore the "network" tab and find where you can compare your predicted request/response components to the actual components.

#### Step 3

If your prediction was wrong, try to understand why it was incorrect and then update your documentation to the correct request/response components.

Congratulations! You have performed a GET request to / showing the home page of our e-commerce
website. Move on to the next request/response documentation.

- Note
  - Headers contain many keys, but for this exercise focus on **Content-Type** and **Location**.

# =============================================

### Ask for a page that doesn't exist

Request components:

- Method: GET
- URL: http://localhost:500/blink
- Headers: none
- Body: none

Response components:

- Status code: 404
- Headers:

  - Content-Type: text/html

- Body: `html with other and 404 client error server status code below`

### Ask for the products list page

Request components:

- Method: GET
- URL: http://localhost:5000/products
- Headers:none
- Body:none

Response components:

- Status code:200
- Headers:
  - Content-Type: text/html
- Body: `html with links to other pages and a list of all products`

### Ask for the product detail page

Here's an example product on the server:

| detail      | value                                                      |
| ----------- | ---------------------------------------------------------- |
| productId   | 1                                                          |
| name        | "Facial Cleansing Brush"                                   |
| description | "Reaches deep pores to cleanse oil, dirt, and blackheads." |
| price       | 23.99                                                      |
| categories  | "beauty", "electronics"                                    |

Request components:

- Method: GET
- URL: http://localhost:5000/products/productId
- Headers: none
- Body: none

Response components:

- Status code: 200
- Headers:
  - Content-Type: text/html
- Body: html with links to other pages and details about the product `product name, product description, product price and product category, a form to add a review on the product`

### Ask for the create new product page

Request components:

- Method: GET
- URL: http://localhost:5000/new
- Headers: none
- Body: none

Response components:

- Status code: 200
- Headers:
  - Content-Type: text/html
- Body: `html with links to other pages, a form to add new product with inputs for product name, product categories, product description, product price`

### Submit a new product

Remember, for a traditional HTML web server, whenever a successful `POST`
request is sent to the server, the server should respond with a redirection to
a page.

After successful submission, user should be looking at the product detail page.

Here are the categories on the server:

| tag         | name           |
| ----------- | -------------- |
| grocery     | Grocery        |
| electronics | Electronics    |
| beauty      | Beauty         |
| toys-games  | Toys and Games |
| health      | Health         |
| furniture   | Furniture      |
| clothing    | Clothing       |

- Note: In Chrome dev tools, if the "body" of a request exists, it will appear
  in the network tab as "payload".

Request components:

- Method: POST
- URL: http://localhost:5000/products/productId
- Headers: none
- Body:
  - name: product name
    -description: product description
  - price: product price
  - categories: product categories

Response components:

- Status code: 302
- Headers:
  - Content-Type: text/html
- Body: `html with links to the other pages, details about the new product submitted, product name, product description, product price and product categories and a form to submit a review`

### Ask for the edit product page

Request components:

- Method: GET
- URL: http://localhost:5000/products/:productId/edit
- Headers: none
- Body: none

Response components:

- Status code: 200
- Headers:
  - Content-Type: text/html
- Body: `html with links to the other pages, a form to edit existing product`

### Submit an edit for an existing product

After successful submission, user should be looking at the product detail page.

Request components:

- Method: POST
- URL: http://localhost:5000/products/:productId
- Headers:none
- Body: name: product name, description:product description, price: product price, categories: product categories

Response components:

- Status code: 302
- Headers:
  - Content-Type: text/html
- Body: `html with links to other pages and the edited product details page`

### Submit a delete for an existing product

After successful submission, user should be looking at the products list page.

Request components:

- Method: POST | PUT | PATCH
- URL: http://localhost:5000/products/productId/delete
- Headers: none
- Body:none

Response components:

- Status code: 302
- Headers:
  - Location: /products
- Body:none

### Submit a new review for a product

After successful submission, user should be looking at the product detail page.

Here's an example review on the server:

| detail     | value                  |
| ---------- | ---------------------- |
| reviewId   | 1                      |
| comment    | "I love this product!" |
| starRating | 5                      |
| productId  | 1                      |

Request components:

- Method: POST
- URL: http:localhost:5000/products/:productId
- Headers:none
- Body: comment: user comment, start-rating: user star rating

Response components:

- Status code: 302
- Headers:
  - Content-Type: text/html
  - Location: products/productId
- Body:none

### Ask for the edit review page for a product

Request components:

- Method: GET
- URL:http://localhost:5000/reviews/reviewId/edit
- Headers:none
- Body:none

Response components:

- Status code: 200
- Headers:
  - Content-Type: text/html
- Body:`html with other links and a form to edit review`

### Submit an edit for an existing review

After successful submission, user should be looking at the product detail page.

Request components:

- Method: POST | PATCH | PUT
- URL: http://localhost:5000/reviews/productId
- Headers: none
- Body: comments: user edited comment or user current comment, rating: user edited rating or user current rating

Response components:

- Status code: 302
- Headers:
  - Content-Type: text/html
  - Location: products/productId
- Body: `html with links to other pages and details about the reviewed product`

### Submit a delete for an existing review

After successful submission, user should be looking at the product detail page.

Request components:

- Method: POST | DELETE
- URL: reviews/productId/delete
- Headers: none
- Body: none

Response components:

- Status code: 302
- Headers:
  - Content-Type: text/html
- Body: `html with links to other pages and the product details page`

### Ask for all the products in a particular category by tag of the category

Request components:

- Method:GET
- URL: products/category
- Headers: none
- Body: none

Response components:

- Status code: 200
- Headers:
  - Content-Type: text/html
- Body: `html with links to other pages and a list of products of the chosen category`

### Ask for the best-selling product

Look for clues in the HTML pages from the prior responses for what the route should be.

Request components:

- Method:GET
- URL: products/category
- Headers: none
- Body: none

Response components:

- Status code: 200
- Headers:
  - Content-Type: text/html
- Body: `html with links to other pages and a list of products of the chosen category`
