<div align="center">
  <img src="https://images.unsplash.com/photo-1653717672381-efe4015b5e1b?q=80&w=3132&auto=format&fit=crop&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="newsletter" width="600" />
  <h1>Your First Express.js API</h1>
</div>


### 🎯 Objective

Welcome to your first hands-on assignment with Express.js! In this assignment, you will create a small backend application that exposes several API endpoints to perform basic operations such as addition, sorting arrays, and doing arithmetic calculations.

This will help you:

* Set up and run an Express.js app
* Understand how to define routes
* Learn how to receive input via query parameters and JSON bodies
* Practice returning structured JSON responses

---

### 📚 What You Need to Do

Create a single file (e.g., `app.js`) that sets up an Express server and defines **three API routes**. You should **keep all the code in a single file** — there's no need to split it into multiple modules yet.

Your Express app should expose the following endpoints:

---

### 1. `GET /api/sum`

**Description:** Adds two numbers and returns the result.

**Input:**
Use **query parameters**:

* `a` (number)
* `b` (number)

**Example Request:**

```
GET /api/sum?a=10&b=15
```

**Example Response:**

```json
{
  "result": 25
}
```

---

### 2. `POST /api/sort`

**Description:** Sorts a list of numbers in either ascending or descending order.

**Input:**
Send a **JSON body** with:

* `numbers`: an array of numbers
* `order`: a string `"asc"` or `"desc"`

**Example Request Body:**

```json
{
  "numbers": [8, 3, 5, 1],
  "order": "asc"
}
```

**Example Response:**

```json
{
  "result": [1, 3, 5, 8]
}
```

---

### 3. `POST /api/calculate`

**Description:** Performs a basic math operation between two numbers.

**Input:**
Send a **JSON body** with:

* `a`: first number
* `b`: second number
* `operation`: a string with one of the following values: `"add"`, `"subtract"`, `"multiply"`, `"divide"`

**Example Request Body:**

```json
{
  "a": 10,
  "b": 5,
  "operation": "multiply"
}
```

**Example Response:**

```json
{
  "result": 50
}
```

---

### 🚦Instructions

1. Use **Express.js** to build the server.
2. All your code should be inside a single file called `app.js`.
3. You may use Postman, Thunder Client, or `curl` to test your APIs.

---

### ✅ Bonus (Optional)

Add a new route:

#### `GET /api/fibonacci?n=5`

**Description:** Returns the first `n` numbers in the Fibonacci sequence.
**Example Response:**

```json
{
  "result": [0, 1, 1, 2, 3]
}
```

---

### 📦 Submission Guidelines
* Push your code to a GitHub repository and share the link.

