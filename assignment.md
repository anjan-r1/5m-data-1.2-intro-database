# Assignment

## Brief

Create an ERD for each of the following case study question.

## Instructions

Paste the answer as DBML in the answer code section below each question.

### Question 1

Construct an ERD for a social media company whose database includes information about users, their followers, and the posts that they make. Users can follow multiple users and create multiple posts.

Each entity has the following attributes:

- User: id, username, email, created_at
- Post: id, title, body, user_id, status, created_at
- Follows: following_user_id, followed_user_id, created_at

Answer:

```dbml
table user {
  id int [pk]
  username varchar
  email varchar
  created_at datetime
}

table post {
  id int [pk]
  title varchar
  body text
  user_id varchar 
  status varchar 
  created_at datetime
}

table follows {
  following_user_id varchar [pk]
  followed_user_id varchar [pk]
  created_at datetime
}

Ref: user.id < post.user_id //one user - multiple posts
Ref: user.id < follows.following_user_id // one user - multiple followers
Ref: user.id < follows.followed_user_id // one user - multiple followed


```

### Question 2

Construct an ERD for a company that sells books online. The company has a website where customers can browse available books and add them to their shopping carts. Each cart can contain multiple books.

There are 4 entities, think of what attributes each entity should have.

- Customer
- Book
- Cart
- CartItem

Answer:

```dbml
table customer {
  customer_id int [pk]
  name varchar
  address text
  email_id varchar
  phone_number varchar
  gender varchar
  customer_since date
}

table cart {
  cart_id int [pk]
  customer_id int
}

table cart_item {
  cart_id int [pk]
  book_id int [pk]
  quantity int 
}

table book {
  book_id int [pk]
  isbn varchar
  title varchar
  author varchar
  publisher varchar
  publishing_year year
  price decimal
}

Ref: customer.customer_id - cart.customer_id // one customer can have one cart
Ref: cart.cart_id < cart_item.cart_id // one cart can have multiple items
Ref: cart_item.book_id - book.book_id // one cart item represents one book 


```

## Submission

- Submit the URL of the GitHub Repository that contains your work to NTU black board.
- Should you reference the work of your classmate(s) or online resources, give them credit by adding either the name of your classmate or URL.
