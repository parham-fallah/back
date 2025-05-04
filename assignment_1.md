# 🧪 Node.js Assignment: Car Market Data Processor

## 🎯 Objective

In this assignment, you'll develop a Node.js application that generates a comprehensive report for the second-hand car market using live API data.

---

## 📝 Steps to Follow

### 🔧 Project Setup

1. Create a GitHub repository and clone it to your local system.
2. Run `npm init -y` to initialize the project.
3. Create an entry file, e.g., `index.js`.
4. Update the `package.json` file to include the following start script:

   ```json
   "scripts": {
     "start": "node index.js"
   }
   ```
5. Create a `.gitignore` file and make sure to exclude the `node_modules/` directory.
6. Install `axios` using:

   ```bash
   npm install axios
   ```

---

## 🌐 Fetching Data

Write 3 separate functions to fetch data from APIs using `axios`:

### 1. Get Cars Data

**Endpoint:** `Get https://lm-models.s3.ir-thr-at1.arvanstorage.ir/cars.json`

**Schema:**

```json
[
  {
    "id": 1,
    "brand": "Toyota",
    "model": "Corolla",
    "year": 2018,
    "mileage": 85000,
    "fuel": "Gasoline",
    "color": "White",
    "price": 850000000
  }
]
```

**Field Descriptions:**

* `id`: Unique identifier for each car
* `brand`: Manufacturer brand
* `model`: Model name
* `year`: Year of manufacture
* `mileage`: Distance the car has traveled (km)
* `fuel`: Fuel type (e.g., Gasoline, Diesel)
* `color`: Color of the car
* `price`: Listed price in IRR

### 2. Get Market Price Data

**Endpoint:** `Get https://lm-models.s3.ir-thr-at1.arvanstorage.ir/market_prices.json`

**Schema:**

```json
[
  {
    "brand": "Toyota",
    "model": "Corolla",
    "year": 2018,
    "average_price": 900000000,
    "average_mileage": 78000
  }
]
```

**Field Descriptions:**

* `brand`, `model`, `year`: Identifiers to match with a car
* `average_price`: Market average price in IRR
* `average_mileage`: Market average mileage (km)

### 3. Get Currency Data

**Endpoint:** `GET https://baha24.com/api/v1/price`

**Schema:**

```json
{
  "USD": {
    "title": "دلار آمریکا",
    "symbol": "USD",
    "buy": 61000,
    "sell": 61500,
    "last_update": "2025-05-04 11:44"
  }
}
```

**Field Descriptions:**

* `symbol`: Currency abbreviation
* `buy`: Buy price in IRR
* `sell`: Sell price in IRR
* `last_update`: Timestamp of last update

Make sure your functions return the data correctly and handle errors gracefully.

---

## 🔄 Data Processing

Once you have all the data:

### Enrich Each Car with:

* `price_diff_from_average`: Car price minus market average price. If no average found, set to 0.
* `mileage_diff_from_average`: Car mileage minus market average mileage. If not available, set to 0.
* `price_usd`: Car price converted to USD using the Rial to USD rate.

Then store the resulting data in `cars_data.json` in the project root.

---

## 🔍 Data Analysis Questions

Answer the following questions using the processed data. Print answers to the terminal:

### Q1:

Which car brand & model exists the most?

### Q2:

What are the top 3 most expensive cars by brand and model?

### Q3:

What is the USD price difference between the most expensive and cheapest car?

### Q4:

How many cars exist for each color?

### Q5:

For each car (brand & model), which one has the lowest price **and** mileage?

### Q6:

What are the top 5 most fair-priced cars? (Smallest `price_diff_from_average`)

### Q7:

What are the top 5 cars with most fair mileage? (Smallest `mileage_diff_from_average`)

---

## ⏱️ Final Step

After completing all of the above tasks, measure how long your application takes to run. At the beginning of your index.js, capture the current timestamp in milliseconds using Date.now(). At the end of the application, capture the timestamp again and subtract the two to calculate total execution time in seconds. Log the total time in the terminal.

Example:

```js
const startTime = Date.now();

// ... your main code logic ...

const endTime = Date.now();
const executionTime = ((endTime - startTime) / 1000).toFixed(2);
console.log(`Execution completed in ${executionTime} seconds.`);
```

---

## 🚀 Submission Instructions

* Push your code to your GitHub repository.
* Include a `README.md` file that explains how to run your script.
* Submit the GitHub link via the course portal.

---

## 🛠️ Tips

* Use `fs/promises` for file I/O
* Structure your code in clear reusable functions
* Commit often and write clear commit messages

---
