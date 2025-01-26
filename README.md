# alx-project-0x14  

## API Overview

The MoviesDatabase API provides an extensive collection of movie-related data, including movie details, actors, directors, genres, ratings, and more. It is designed for developers to integrate movie information into their applications seamlessly. The API supports features like searching for movies, retrieving detailed movie data, and accessing trending or top-rated content.  

### KEY FEATURES  

-Get Movies: Fetch a list of movies based on title, genre, or release year.  
-User Favorites: Allow users to add movies to their favorites list.  
-Actor Information: Retrieve details about actors, including their filmography.  
-Genre Listing: Access a list of available movie genres.  
-Detailed Movie Data: Get comprehensive information about a specific movie.  

## API Version  

The current version of the MoviesDatabase API is v1.0.  

## Available Endpoints  

1. GET/movies
-Fetches a list of movies based on query parameters like title, genre, or release year.  
2. GET/movies/{id}  
-Retrieves detailed information about a specific movie by its ID.  
3. GET/actors  
-Returns a list of actors and their basic details.  
4. GET/genres  
-Lists all available genres.
5. POST/favorites  
-Allows users to add a movie to their favorites list (requires authentication).  

## Response and Request Format  

### Request Format  

Requests are typically made using HTTP methods like GET, POST, or DELETE. Query parameters or JSON bodies are used to pass data.  

example: GET <https://api.moviesdatabase.com/movies?title=Inception&year=2010>

### Response format  

Responses are typically provided in JSON format.  

example: {
  "id": "12345",
  "title": "Inception",
  "genre": ["Action", "Sci-Fi"],
  "release_year": 2010,
  "rating": 8.8
}

## Authentication  

Authentication is required for accessing most endpoints. The API uses an API key-based system.  
-Generate your API key by creating an account on the MoviesDatabase platform.  
-Include the key in the Authorization header of your requests.  
-Ensure your API key is kept secure and not exposed in client-side code.  

## Error Handling  

The MoviesDatabase API uses standard HTTP status codes to indicate the success or failure of a request.  

Common errors:  

1. 400 Bad request  
Caused by an invalid or missing parameter. Resolved by verifying the required parameters in your request.  
2. 401 Unauthorized  
Caused by missing or an invalid API key. Resolved by including a valid API key in the Autorization header.
3. 429 Too many Requests  
Caused by requests exceeding the rate limit. Resolved by respecting the API's rate limits; implement exponential backoff.  

## Usage Limits and Best practices

1. Rate limits:-  

    The API enforces a rate limit of 100 requests per
    minute per API key.
    Exceeding this limit will result in a 429 Too Many Requests error.

2. Best practices:-  

    Cache frequent requests to minimize API usage.
    Always validate API responses before processing.
    Use paginated requests for endpoints that return large datasets.
