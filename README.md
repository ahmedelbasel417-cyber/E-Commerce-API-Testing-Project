E-Commerce API Testing Project
1. Project Summary

API testing project built with Postman and MockAPI to validate CRUD operations for a product management system.
Tests include request validation, response verification, and automation using environment variables.

2. Goals

Validate that all CRUD endpoints return correct status codes and data.

Automate test flow without manual input.

Use Postman variables to chain requests dynamically.

Document and organize API test cases clearly.

3. Tech Stack

Postman for request execution and automation

MockAPI for mock server and endpoints

JavaScript for Postman test scripts

JSON for data formatting and structure

4. API Endpoints Tested
Method	Endpoint	Purpose
POST	/products	Create new product
GET	/products	Retrieve all products
GET	/products/:id	Retrieve product by ID
PUT	/products/:id	Update product
DELETE	/products/:id	Delete product
5. Example Test Script
let responseData = pm.response.json();
pm.environment.set("product_id", responseData.id);

pm.test("Status code is 201", function () {
    pm.response.to.have.status(201);
});

pm.test("Response has product ID", function () {
    pm.expect(responseData).to.have.property("id");
});

6. Automation Flow

Create all requests in one Postman collection.

Set environment variables:

base_url → MockAPI base link

product_id → dynamically stored after POST request

Run collection using Postman Collection Runner.

Observe results and validate JSON responses automatically.

7. Key Results

Full CRUD operations automated.

Dynamic data passing validated.

Status code and response structure checks implemented.

Easily reusable setup for any REST API.

8. How to Run

Import E-Commerce.postman_collection.json into Postman.

Import MockAPI_environment.json into Environments.

Set the environment before running.

Open Collection Runner and run all requests.