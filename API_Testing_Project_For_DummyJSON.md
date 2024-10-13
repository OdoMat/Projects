<h1>API Testing Project for DummyJSON</h1>

The scope of this project is to use all  API knowledge gained throught the Software Testing course and apply them in practice, using a live application.

Application under test: DummyJSON

Tools used: Postman, Newman

Collection link: https://dummyjson.com/docs

<h2>Tests performed</h2>

<ol>
<li>Get All Products</li>

HTTP method for request: GET https://dummyjson.com/products <br>
Request description: This request retrieves a list of all products.<br>
Test types / techniques used: Functional Testing, Performance Testing, Reliability Testing, Data Integrity Testing / Equivalence Partitioning, Boundary Value Analysis, Data Validation<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![all products](https://github.com/user-attachments/assets/b1a6b810-730d-4587-9521-4438103ff3db)<br>

JavaScript Tests:

![all products tests](https://github.com/user-attachments/assets/e31f1cee-c54b-49d4-bf75-835dd633b1ad)<br>


<li>GET Product by ID</li>

HTTP method for request: GET https://dummyjson.com/products/1.<br>
Request description: This request retrieves details of the product with ID 1<br>
Test types / techniques used: Functional Testing, Performance Testing, Validation Testing / Boundary Value Analysis, Data Validation<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![product by ID](https://github.com/user-attachments/assets/5675ec31-a94b-400b-b9bf-a427f59f719e)<br>

JavaScript Tests:

![product by id tests](https://github.com/user-attachments/assets/de658059-df5c-4bf2-aa8e-dcf8b8537a60)<br>


<li>GET Product by Non-Existent ID</li>

HTTP method for request: GET https://dummyjson.com/products/78904.<br>
Request description: This request attempts to retrieve details of a non-existient ID(78904)<br>
Test types / techniques used: Functional Testing, Performance Testing / Status Code Verification, Boundary Value Analysis, Error message Validation<br>
Response status code: 404 NOT FOUND<br>

Below you can find a picture of the API request from Postman:<br>

![product by non-existent ID](https://github.com/user-attachments/assets/671a6b6c-4f83-4556-9f50-3af694480626)<br>

JavaScript Tests:

![product by non-existent id tests](https://github.com/user-attachments/assets/924c0a9b-1c4e-42ab-a2de-8935a2d586a4)<br>


<li>GET All Products Categories </li>

HTTP method for request: GET https://dummyjson.com/products/categories.<br>
Request description: This request retrieves a list of all product categories<br>
Test types / techniques used: Functional Testing, Performance Testing / Boundary Value Analysis, Validation<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![all categories](https://github.com/user-attachments/assets/2cac2e3b-f525-4b27-9f5c-b192a7af23d2)<br>

JavaScript Tests:

![all categories tests](https://github.com/user-attachments/assets/7ab2a433-175e-4377-89c9-8a20e06a3e5e)
<br>


<li>GET Products by Specific Category</li>

HTTP method for request: GET https://dummyjson.com/products/category/smartphones <br>
Request description: This request retrieves a list of all products from the smartphones category.<br>
Test types / techniques used: Functional Testing, Performance Testing / Boundary Value Analysis, Validation<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![products by category](https://github.com/user-attachments/assets/ba0f6e19-2923-48a0-a891-ff461a590fc3)<br>

JavaScript Tests:

![products by category tests](https://github.com/user-attachments/assets/0818b171-b908-479a-aa6b-a08f6bf6270b)<br>

<li>GET Products by Non-Existent Category</li>

HTTP method for request: GET https://dummyjson.com/products/category/smartphones <br>
Request description: This request attempts to  retrieve a list of all products from the non-existent category (Jeans).<br>
Test types / techniques used: Functional Testing, Performance Testing / Boundary Value Analysis, Validation<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![pruducts by non existent category](https://github.com/user-attachments/assets/7f273283-163c-4893-8fa3-ae7dd1f1406c)<br>

JavaScript Tests:

![products by non existent category tests](https://github.com/user-attachments/assets/4689cf32-afbf-4751-abbc-65df7838a1fe)<br>


<li>GET Products That Match the Query Hoodie</li>

HTTP method for request: GET https://dummyjson.com/products/search?q=hoodie <br>
Request description: This request retrieves only the products related to non-existent product "hoodie".<br>
Test types / techniques used: Functional Testing, Performance Testing / Negative Testing, Response Validation<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![products non existent](https://github.com/user-attachments/assets/b3e71b2c-55ef-4fd9-91fd-0329bebe29e4)<br>

JavaScript Tests:

![products non existent tests](https://github.com/user-attachments/assets/50f7ac58-74ef-4b4b-ac31-25a347d72b90)<br>


<li>Create New Product </li>

HTTP method for request: POST https://dummyjson.com/products/add <br>
Request description: This request will create a new product.<br>
Test types / techniques used: Functional Testing, Performance Testing / Positive Testing, Boundary Value Analysis<br>
Response status code: 201 CREATED<br>

Below you can find a picture of the API request from Postman:<br>

![create product](https://github.com/user-attachments/assets/6536ca48-825a-47b0-9c9d-84754d64545c)<br>

JavaScript Tests:

![create product tests](https://github.com/user-attachments/assets/304d9455-af23-43e7-b990-273b466aeb6d)<br>


<li>Create New Product With Invalid Data </li>

HTTP method for request: POST https://dummyjson.com/products/add <br>
Request description: This request will attempt to create a new product with invalid data.<br>
Test types / techniques used: Functional Testing, Performance Testing / Negative Testing, Error Guessing<br>
Response status code: 201 CREATED<br>

Below you can find a picture of the API request from Postman:<br>

![create product invalit data](https://github.com/user-attachments/assets/15d0d7ae-ee8f-4cec-a0e4-aacb937183c6)<br>

JavaScript Tests:

![product Invalid Data Tests](https://github.com/user-attachments/assets/45cf1814-f63b-41c5-b450-83f8cd2a094d)<br>


<li>Update Product by ID</li>

HTTP method for request: PUT https://dummyjson.com/products/1<br>
Request description: This request will update the product with ID 1.<br>
Test types / techniques used: Functional Testing, Performance Testing, Regression Testing / Positive Testing, Boundary Value Analysis<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![Update product](https://github.com/user-attachments/assets/0f031761-a3cb-464f-9b13-bcb25add50f4)<br>

JavaScript Tests:

![update product tests](https://github.com/user-attachments/assets/e0493a17-055a-4e5a-a1a5-5c65bd6b9071)<br>


<li>Update Product by  Invalid ID</li>

HTTP method for request: PUT https://dummyjson.com/products/9999<br>
Request description: This request will attempt to update the product with the invalid ID 9999.<br>
Test types / techniques used: Functional Testing, Performance Testing / Negative Testing, Boundary Value Analysis<br>
Response status code: 404 NOT FOUND<br>

Below you can find a picture of the API request from Postman:<br>

![update non existent](https://github.com/user-attachments/assets/53aee2a1-e1d2-4e34-be1b-be95ef7cd5c0)<br>

JavaScript Tests:

![updatet non existent tests](https://github.com/user-attachments/assets/542e043f-f637-403c-af56-2adf8daf7a11)<br>


<li>Partially Update Product by ID</li>

HTTP method for request: PATCH https://dummyjson.com/products/1<br>
Request description: This request will partially update the product with ID 1.<br>
Test types / techniques used: Functional Testing, Performance Testing, Regression Testing / Positive Testing, Boundary Value Analysis<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![partialy update](https://github.com/user-attachments/assets/2a1ac5de-1334-4d09-bab5-990293dd7b34)<br>

JavaScript Tests:

![partialy update tests](https://github.com/user-attachments/assets/dae7f55d-b332-4390-a315-573232a43b8a)<br>


<li>Partially Update Product With Invalid Data</li>

HTTP method for request: PATCH https://dummyjson.com/products/1<br>
Request description: This request will attempt to partially update the product with ID 1 with invalid data.<br>
Test types / techniques used: Functional Testing, Performance Testing / Negative Testing, Boundary Value Analysis<br>
Response status code: 400 BAD REQUEST<br>

Below you can find a picture of the API request from Postman:<br>

![partialy invalid data](https://github.com/user-attachments/assets/76b09cbc-c183-48e1-91b7-5bb2847ca178)<br>

JavaScript Tests:

![partially invalid tests](https://github.com/user-attachments/assets/335e5b69-d6d7-4597-99a0-788f8d8fa5f8)<br>


<li>Delete Product by ID</li>

HTTP method for request: DELETE https://dummyjson.com/products/1
Request description: This request will detele the product with ID 1.<br>
Test types / techniques used: Functional Testing, Performance Testing / Positive Testing<br>
Response status code: 200 OK<br>

Below you can find a picture of the API request from Postman:<br>

![delete](https://github.com/user-attachments/assets/5e46e9c4-6d84-49b6-877c-ffff63300cb1)<br>

JavaScript Tests:

![delete tests](https://github.com/user-attachments/assets/c4468e84-fa3b-4b03-8a51-48d6c5c0e31e)
<br>

<li>Delete Product by Invalid ID</li>

HTTP method for request: DELETE https://dummyjson.com/products/975567
Request description: This request will attempt to detele the product with invalid ID 875567.<br>
Test types / techniques used: Functional Testing, Performance Testing / Negative Testing<br>
Response status code: 404 NOT FOUND<br>

Below you can find a picture of the API request from Postman:<br>

![delete invalid](https://github.com/user-attachments/assets/1aeb499b-f048-4b18-b040-1aec8bac0eee)<br>

JavaScript Tests:

![delete unexisting](https://github.com/user-attachments/assets/1ba2e854-4f29-4bfd-b5d8-9896a3ea38c9)<br>

</ol>

<h2>Execution report for the created API collection </h2>

Below you can find the execution report that was generated through the Postman collection runner. <br>

![execution runner](https://github.com/user-attachments/assets/e617581d-81c4-400c-9436-7b59315563ea)<br>

The collection was also run through newman directly from the terminal, and the results can be found below:<br>

![newman](https://github.com/user-attachments/assets/15945cd4-5bbf-4ffb-a3cc-5671f80b2d8c)<br>

<h2>Defects found</h2>

The following issues were identified while running the postman tests:<br>

[Bugs.pdf](https://github.com/user-attachments/files/17354925/Bugs.pdf)


<h2>Conclusions</h2>

In this project, I tested the DummyJSON application`s API using postman to manage API requests and define tests. For running the execution report, I utilized both the Collection Runner directly from Postman and Newman.
I executed 15 HTTP requests and 65 tests, of which 56 tests ran succesfully while 9 failed. Upon analyzing the results, I identified 5 bugs, including:

          - The request for a non-existent product category returns a status code of 200 instead 404.
          - Creating a new product with invalid data is permited.
          - The error message is not returned.
          - A product can be updated without some of the required fields such as price, category etc.
          - A product can be partially updated with invalid data.
          
These bugs highlight fundamental issues with validation and error handling in the API.
The lack of  proper validation can lead to unpredictable application behavior, allowing inconsistent or incomplete data in the database. Aditionally, incorrect status code response can mislead users.
In conclusion, launching the application without addressing these bugs could significantly impact functionality and user trust.


