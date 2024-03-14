# KYC360-Assignment Explanation of my code
It defines a controller named EntitiesController, which handles CRUD (Create, Read, Update, Delete) operations for managing entities. The entities are modeled using the Entity class and related classes for addresses, dates, and names.
Let's break down the logic of the code:
# 1.	CRUD Endpoints:
•	CreateEntity: Handles the HTTP POST request to create a new entity. It adds the entity to the entities list and returns a success response.<br>
•	GetAllEntities: Handles the HTTP GET request to fetch all entities from the entities list and returns them.<br>
•	GetEntityById: Handles the HTTP GET request to fetch a single entity by its ID from the entities list and returns it. If the entity is not found, it returns a 404 Not Found response.<br>
•	UpdateEntity: Handles the HTTP PUT request to update an existing entity by its ID. It finds the entity in the entities list, updates its properties with the provided values, and returns a success response. If the entity is not found, it returns a 404 Not Found response.<br>
•	DeleteEntity: Handles the HTTP DELETE request to delete an existing entity by its ID. It finds the entity in the entities list, removes it, and returns a success response. If the entity is not found, it returns a 404 Not Found response.
# 2.	Search and Filtering Endpoints:
•	SearchEntities: Handles the HTTP GET request to search for entities based on the provided search query. It performs a case-insensitive search across entity names and addresses and returns matching entities.<br>
•	FilterEntities: Handles the HTTP GET request to filter entities based on optional query parameters such as gender, start date, end date, and countries. It applies filters based on the provided parameters and returns filtered entities.
# 3.	Entity Model Classes:
•	Entity: Represents an entity with properties like addresses, dates, deceased status, ID, and names.<br>
•	Address, Date, Name: Classes representing address, date, and name properties of an entity.<br>
Example:
Assuming the API is hosted at http://localhost:5000, here are some example requests:

• Creating an entity: <br>
`POST http://localhost:5000/api/entities`<br>
`Body: { "Id": "1", "Names": [{ "FirstName": "John", "Surname": "Doe" }], "Addresses": [{ "Country": "USA" }] }`

• Getting all entities:<br>
`GET http://localhost:5000/api/entities`

• Getting a single entity by ID:<br>
`GET http://localhost:5000/api/entities/1`

• Updating an entity by ID:<br>
`PUT http://localhost:5000/api/entities/1`<br>
`Body: { "Id": "1", "Names": [{ "FirstName": "John", "Surname": "Doe" }], "Addresses": [{ "Country": "Canada" }] }`

• Deleting an entity by ID:<br>
`DELETE http://localhost:5000/api/entities/1`

• Searching entities:<br>
`GET http://localhost:5000/api/entities/search?search=John`

• Filtering entities:<br>
`GET http://localhost:5000/api/entities/filter?gender=Male&countries=USA`
