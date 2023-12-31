**Address Book API**

The Address Book API is a simple REST API built using FastAPI and SQLite that allows users to create, update, and delete addresses. It also provides a way for users to retrieve addresses within a given distance and location coordinates.

**Requirements:**

- Python 3.7 or higher
- Install the necessary libraries: fastapi, uvicorn, pydantic, geopy, and sqlite3. You can install all of these libraries by running the command `pip install -r requirements.txt` from your terminal.

**How to Run the API:**

1. Clone the repository or download the code.
2. Navigate to the project directory in your terminal.
3. Install the necessary libraries using the command `pip install -r requirements.txt`.
4. Run the API using the command `uvicorn main:app --reload`. 
5. Navigate to `http://localhost:8000/docs` in your web browser to access the Swagger UI and interact with the API. 

**API Endpoints:**

The API has the following endpoints:

1. `POST /addresses`: Create a new address. Expects a JSON body with the following fields:
   - `street`: The street address.
   - `city`: The city name.
   - `state`: The state name.
   - `zip`: The ZIP code.
   - `latitude`: The latitude of the address.
   - `longitude`: The longitude of the address.

2. `PUT /addresses/{address_id}`: Update an existing address. Expects a JSON body with the same fields as the `POST` endpoint, and a path parameter `address_id` with the ID of the address to update.

3. `DELETE /addresses/{address_id}`: Delete an address. Expects a path parameter `address_id` with the ID of the address to delete.

4. `GET /addresses/nearby`: Retrieve addresses within a given distance and location coordinates. Expects query parameters `latitude`, `longitude`, and `distance`, where `latitude` and `longitude` are the coordinates of the location, and `distance` is the radius of the search in miles.

Note: All endpoints expect a JSON response in the same format as the `POST` endpoint.

**Example Usage:**

Create a new address:
```
POST /addresses
{
  "street": "123 Main St",
  "city": "Anytown",
  "state": "NY",
  "zip": "12345",
  "latitude": 40.7128,
  "longitude": -74.0060
}
```



**Conclusion:**

The Address Book API is a simple, easy-to-use API that provides basic CRUD functionality for addresses, as well as the ability to search for nearby addresses by distance and location coordinates.
