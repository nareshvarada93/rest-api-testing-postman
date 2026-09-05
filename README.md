# rest-api-testing-postman
# REST API Testing using Postman

## Project Overview

This project demonstrates functional and automated testing of REST APIs using Postman. The project covers user and post management APIs and validates HTTP methods, status codes, request parameters, request bodies, response data, response structure, response time, and error scenarios.

## Objective

The objective of this project is to design and execute reusable API test cases using Postman and JavaScript assertions while identifying unexpected API behavior and validating API responses.

## Tools & Technologies

* Postman
* REST API
* JSON
* JavaScript
* Git
* GitHub

## API Used

JSONPlaceholder

Base URL:

```text
https://jsonplaceholder.typicode.com
```

JSONPlaceholder is a free fake REST API used for testing and prototyping.

## Testing Scope

The project covers:

* GET requests
* POST requests
* PUT requests
* PATCH requests
* DELETE requests
* Query parameter validation
* Request body validation
* HTTP status code validation
* JSON response validation
* Response field validation
* Response time validation
* Positive test scenarios
* Negative test scenarios
* Error handling
* Environment variables
* JavaScript assertions
* Postman Collection Runner

## API Endpoints Tested

### Users

| Method | Endpoint      | Purpose                  |
| ------ | ------------- | ------------------------ |
| GET    | `/users`      | Retrieve all users       |
| GET    | `/users/1`    | Retrieve a specific user |
| GET    | `/users/9999` | Test invalid user ID     |
| POST   | `/users`      | Create a user            |
| PUT    | `/users/1`    | Update a user            |
| PATCH  | `/users/1`    | Partially update a user  |
| DELETE | `/users/1`    | Delete a user            |

### Posts

| Method | Endpoint          | Purpose                  |
| ------ | ----------------- | ------------------------ |
| GET    | `/posts`          | Retrieve all posts       |
| GET    | `/posts/1`        | Retrieve a specific post |
| GET    | `/posts?userId=1` | Filter posts by user     |
| GET    | `/posts/9999`     | Test invalid post ID     |
| POST   | `/posts`          | Create a post            |
| PUT    | `/posts/1`        | Update a post            |
| DELETE | `/posts/1`        | Delete a post            |

## Test Validation

Postman JavaScript assertions were used to validate:

* HTTP status codes
* Response format
* Required JSON fields
* Returned IDs
* User information
* Post information
* Updated values
* Response time
* Query parameter results

Example assertion:

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

Example response-data validation:

```javascript
pm.test("Correct user ID is returned", function () {
    const data = pm.response.json();
    pm.expect(data.id).to.eql(1);
});
```

## Positive Testing

Positive scenarios include:

1. Retrieve all users.
2. Retrieve a valid user.
3. Create a user.
4. Update a user.
5. Partially update a user.
6. Delete a user.
7. Retrieve all posts.
8. Retrieve a valid post.
9. Create a post.
10. Update a post.
11. Delete a post.
12. Filter posts using a query parameter.

## Negative Testing

Negative scenarios include:

1. Requesting an invalid user ID.
2. Requesting an invalid post ID.
3. Requesting an invalid API endpoint.
4. Testing unexpected or error responses.
5. Validating how the API responds to invalid resources.

Because JSONPlaceholder is a mock API, some invalid-resource responses may differ from a production REST service. The test suite therefore validates the behavior actually returned by the API.

## Environment Variables

The Postman environment contains reusable variables such as:

```text
baseUrl
userId
postId
```

Example:

```text
{{baseUrl}}/users/{{userId}}
```

This makes the collection easier to maintain and reuse.

## Project Structure

```text
rest-api-testing-postman/
│
├── README.md
│
├── Postman/
│   ├── REST_API_Testing.postman_collection.json
│   └── REST_API_Testing.postman_environment.json
│
├── TestCases/
│   └── API_Test_Cases.xlsx
│
└── TestReports/
    └── Test_Execution_Report.md
```

## How to Run the Project

### Step 1

Install Postman.

### Step 2

Clone or download this repository.

### Step 3

Open Postman and import:

```text
REST_API_Testing.postman_collection.json
```

### Step 4

Import/select:

```text
REST_API_Testing.postman_environment.json
```

### Step 5

Select the environment:

```text
REST API Testing Environment
```

### Step 6

Run individual requests to inspect the API responses.

### Step 7

Run the complete collection using Postman Collection Runner.

### Step 8

Review the test execution results and failed assertions.

## Test Execution

The collection was executed using Postman Collection Runner.

Execution results are documented in:

```text
TestReports/Test_Execution_Report.md
```

## Key Learning Outcomes

Through this project, I gained practical experience in:

* REST API testing
* HTTP methods
* API request and response analysis
* JSON validation
* Status code validation
* Positive and negative testing
* API test automation using JavaScript
* Postman collections
* Environment variables
* Query parameter testing
* Debugging unexpected API behavior
* Test execution and reporting
* Git and GitHub project management

## Future Improvements

The project can be extended by:

* Adding schema validation
* Adding data-driven testing
* Integrating Newman for command-line execution
* Integrating API tests with Jenkins
* Generating automated HTML test reports
* Adding the collection to a CI/CD pipeline

## Author

Naresh Varada

Aspiring QA / Test Automation Engineer

Skills: Manual Testing | API Testing | Postman | Java | Python | SQL | Selenium | Git
