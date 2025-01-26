# Product Manage Service with Currency Conversion

This Spring Boot application allows users to store product details in a database and calculate the price of the product in different currencies. The currency exchange rates are fetched from the [VATComply API](https://www.vatcomply.com/documentation).

## Features

- **Save product**: Add a product to the database with properties such as name, category, currency, price, EAN, and ASIN.
- **Retrieve product by ID**: Fetch product details using a unique generated ID.
- **Retrieve all products**: Get a list of all products stored in the database.
- **Price conversion**: Get the price of a product in a different currency than the one stored by fetching the conversion rate from VATComply API.

## Technologies Used

- **Java 21** 
- **Spring Boot 3.4.2** (for building REST API)
- **Spring Data JPA** (for database interaction)
- **PostgreSQL** (for database)
- **RestTemplate** (to fetch exchange rates from VATComply API)
- **Java Package Structure**: Here used same package for all classess related to Product service. Not used different packages for Repository,Service and Controller. 



## Setup Instructions

1. **Clone the repository:**

   ```bash
   git clone https://github.com/Gehan-Atapattu/daifin.git

2. **Change Database Configurations:**
    following 3 fields of application.properties must change as per your settings
   
    spring.datasource.url=jdbc:postgresql://localhost:5432/productdb
   
    spring.datasource.username=xxxxxx
   
    spring.datasource.password=xxxxxx

   
4. **Build Project:**

## API Testing

1. **Create a Product:**
   
     URL: /products
     Method: POST
     ```bash
     {"name": "Product Name","category": "Product Category","currency": "USD","price": 100.0,"ean": "1234567890","asin": "A123456789"}

 2. **Get Produt by ID:**
    
     URL: /products/{id}
    
     Method: GET
    
 3. **Get all Products:**
    
     URL: /products
    
     Method: GET

 4. **Get Product Price in Different Currency:**
    
     URL: /products/{id}/price
    
     Method: GET
    
     Request Parameters: currency: The target currency in which the price should be converted (e.g., EUR).

     ```bash
     GET http://localhost:8080/products/1/price?currency=EUR



   



     

   
