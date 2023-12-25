# Movie CRUD API in Golang

This Go application implements a simple CRUD (Create, Read, Update, Delete) API for managing a movie watchlist using MongoDB. The API provides endpoints for retrieving all movies, adding a new movie, marking a movie as watched, deleting a specific movie, and deleting all movies.

## How to Run

1. Ensure you have Go installed on your machine.
2. Clone this repository.
3. Replace the MongoDB connection string in the code with your actual connection string.
4. Run the application using the `go run main.go` command.

## Routes and Functions

1. **GET /api/movies**

   - **Function:** `GetMyAllMovies`
   - **Description:** Retrieve all movies from the watchlist.
   - **Usage:** `GET /api/movies`

2. **POST /api/movie**

   - **Function:** `CreateMovie`
   - **Description:** Add a new movie to the watchlist.
   - **Usage:** `POST /api/movie`
   - **Request Body Format:** JSON with movie details.

3. **PUT /api/movies/{id}**

   - **Function:** `MarkAsWatched`
   - **Description:** Mark a specific movie as watched.
   - **Usage:** `PUT /api/movies/{id}`
   - **Path Parameter:** `id` (MongoDB ObjectID of the movie)

4. **DELETE /api/movies/{id}**

   - **Function:** `DeleteAMovie`
   - **Description:** Delete a specific movie from the watchlist.
   - **Usage:** `DELETE /api/movies/{id}`
   - **Path Parameter:** `id` (MongoDB ObjectID of the movie)

5. **DELETE /api/deleteallmovies**
   - **Function:** `DeleteAllMovies`
   - **Description:** Delete all movies from the watchlist.
   - **Usage:** `DELETE /api/deleteallmovies`

## MongoDB Setup

The application uses MongoDB as the database for storing movie records.

- **Connection String:** Replace `"xyz"` in the `connectionString` constant with your MongoDB connection string.
- **Database Name:** The database name is set to `"netflix"`.
- **Collection Name:** The collection name is set to `"watchlist"`.

## MongoDB Helper Functions

- **`insertOneMovie(movie model.Netflix)`**

  - Inserts a single movie record into the MongoDB collection.

- **`getAllMovies() []primitive.M`**

  - Retrieves all movies from the MongoDB collection.

- **`updateOneMovie(movieId string)`**

  - Marks a specific movie as watched in the MongoDB collection.

- **`deleteOneMovie(movieId string)`**

  - Deletes a specific movie from the MongoDB collection.

- **`deleteAll() int64`**
  - Deletes all movies from the MongoDB collection.
