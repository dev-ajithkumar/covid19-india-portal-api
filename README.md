This repository contains a code base for a COVID-19 India Portal. The code is written in JavaScript using the Node.js runtime environment. The portal provides functionality to manage and retrieve data related to Indian states and districts affected by COVID-19. It uses the Express framework for handling HTTP requests and SQLite as the database.

### Use Cases

The COVID-19 India Portal code allows users to perform the following actions:

1. **User Authentication**: Users can log in to the portal using their username and password. The passwords are securely stored using bcrypt for hashing and comparing.

2. **Retrieve States**: Users can retrieve a list of all states in India along with their details, such as state ID, state name, and population.

3. **Retrieve State by ID**: Users can retrieve details of a specific state by providing its ID.

4. **Add District**: Users with appropriate authentication can add a new district to the database by providing details such as district name, state ID, COVID-19 cases, cured cases, active cases, and deaths.

5. **Retrieve District by ID**: Users can retrieve details of a specific district by providing its ID.

6. **Delete District**: Users with appropriate authentication can delete a district from the database by providing its ID.

7. **Update District**: Users with appropriate authentication can update the details of a district by providing its ID and the updated information.

8. **Retrieve State Statistics**: Users can retrieve statistics for a specific state, including the total number of cases, cured cases, active cases, and deaths.

### Prerequisites

Before using the COVID-19 India Portal, make sure you have the following dependencies installed:

- Node.js: You can download and install Node.js from the official website: https://nodejs.org

### Getting Started

To use the COVID-19 India Portal, follow these steps:

1. Clone the repository to your local machine or download the code as a ZIP file.

2. Open a terminal or command prompt and navigate to the project's directory.

3. Install the project dependencies by running the following command:

   ```
   npm install
   ```

4. Start the server by running the following command:

   ```
   node app.js
   ```

   The server will start running at http://localhost:3000.

### API Endpoints

The COVID-19 India Portal exposes the following API endpoints:

- `POST /login/`: Authenticates the user by checking the username and password in the request body. Returns a JWT token on successful authentication.

- `GET /states/`: Retrieves a list of all states in India with their details.

- `GET /states/:stateId/`: Retrieves details of a specific state by providing its ID.

- `POST /districts/`: Adds a new district to the database. Requires authentication. The district details should be provided in the request body.

- `GET /districts/:districtId/`: Retrieves details of a specific district by providing its ID.

- `DELETE /districts/:districtId/`: Deletes a district from the database. Requires authentication. Provide the district ID in the URL.

- `PUT /districts/:districtId/`: Updates the details of a district. Requires authentication. Provide the district ID in the URL and the updated details in the request body.

- `GET /states/:stateId/stats/`: Retrieves statistics for a specific state, including the total number of cases, cured cases, active cases, and deaths.

### Examples

Here are some examples to help you understand how to use the COVID-19 India Portal.

**1. Authenticate User**

- Endpoint: `POST /login/`

- Request Body:
  ```json
  {
    "username": "john_doe",
    "password": "password",
  }
  ```

````

- Response:
  ```json
  {
    "jwtToken": "<token>"
  }
````

Store the `jwtToken` for authentication purposes in subsequent requests.

**2. Retrieve States**

- Endpoint: `GET /states/`

- Response:
  ```json
  [
    {
      "stateId": 1,
      "stateName": "Andhra Pradesh",
      "population": 53903393
    },
    {
      "stateId": 2,
      "stateName": "Arunachal Pradesh",
      "population": 1570458
    }
  ]
  ```

**3. Retrieve State by ID**

- Endpoint: `GET /states/:stateId/`

- Replace `:stateId` in the URL with the desired state ID.

- Response:
  ```json
  {
    "stateId": 1,
    "stateName": "Andhra Pradesh",
    "population": 53903393
  }
  ```

**4. Add District**

- Endpoint: `POST /districts/`

- Request Body:

  ```json
  {
    "districtName": "Chennai",
    "stateId": 1,
    "cases": 5000,
    "cured": 4500,
    "active": 450,
    "deaths": 50
  }
  ```

- Response:
  ```
  District Successfully Added
  ```

**5. Retrieve District by ID**

- Endpoint: `GET /districts/:districtId/`

- Replace `:districtId` in the URL with the desired district ID.

- Response:
  ```json
  {
    "districtId": 1,
    "districtName": "Chennai",
    "stateId": 1,
    "cases": 5000,
    "cured": 4500,
    "active": 450,
    "deaths": 50
  }
  ```

**6. Delete District**

- Endpoint: `DELETE /districts/:districtId/`

- Replace `:districtId` in the URL with the ID of the district to be deleted.

- Response:
  ```
  District Removed
  ```

**7. Update District**

- Endpoint: `PUT /districts/:districtId/`

- Replace `:districtId` in the URL with the ID of the district to be updated.

- Request Body:

  ```json
  {
    "districtName": "Mumbai",
    "stateId": 2,
    "cases": 6000,
    "cured": 5500,
    "active": 400,
    "deaths": 100
  }
  ```

- Response:
  ```
  District Details Updated
  ```

**8. Retrieve State Statistics**

- Endpoint: `GET /states/:stateId/stats/`

- Replace `:stateId` in the URL with the desired state ID.

- Response:
  ```json
  {
    "totalCases": 10000,
    "totalCured": 9000,
    "totalActive": 800,
    "totalDeaths": 200
  }
  ```

Feel free to explore other endpoints and experiment with different requests based on your requirements.

### Conclusion

The COVID-19 India Portal provides a simple yet effective way to manage and retrieve data related to COVID-19 cases in Indian states and districts. With the provided API endpoints, you can authenticate users, retrieve state and district information, add new districts, update existing districts, and retrieve statistics. The

code is designed to be beginner-friendly and easy to understand.
