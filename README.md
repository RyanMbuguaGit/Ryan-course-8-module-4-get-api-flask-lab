# RESTful GET API with Flask

A simple Flask REST API for browsing a fictional product catalog. Built as part of Module 5 (Software Engineering Full Time) — Lab: Building RESTful GET APIs with Flask.

## What It Does

This API exposes a small set of GET endpoints for retrieving product data from an in-memory mock dataset. It demonstrates core REST principles: resource-based routing, dynamic path parameters, query string filtering, and JSON responses.

## Requirements

- Python 3
- Flask

## Setup

1. Clone the repository:

   git clone https://github.com/RyanMbuguaGit/Ryan-course-8-module-4-get-api-flask-lab.git
   cd Ryan-course-8-module-4-get-api-flask-lab

2. Install dependencies:

   pip install flask

3. Run the app:

   python app.py

4. The server starts at http://localhost:5000.

## Endpoints

| Method | Route | Description |
|--------|-------|-------------|
| GET | `/` | Returns a welcome message |
| GET | `/products` | Returns all products; supports optional `?category=` filter |
| GET | `/products/<id>` | Returns a single product by ID, or a 404 error if not found |

## Examples

**Get all products**

GET /products

Returns the full list of products as JSON.

**Filter products by category**

GET /products?category=books

Returns only products whose category matches "books" (case-insensitive).

**Get a single product by ID**

GET /products/2

Returns the product with ID 2, or a JSON error with a 404 status if no product matches.

## Error Handling

Requesting a product ID that doesn't exist returns:

{
  "error": "Product not found"
}

with an HTTP 404 status code.

## Project Structure

.
├── app.py          # Flask app and route definitions
├── data.py         # Mock product data
├── tests/          # Test suite
└── README.md

## Notes

- Category filtering is case-insensitive (e.g. `?category=Books` and `?category=books` return the same results).
- This is a development server only — not intended for production use.