## API Overview

The API provides a comprehensive and regularly updated database that covers more than nine million titles, including movies, TV series, and episodes, as well as information on over eleven million actors, crew, and cast members. It includes useful details such as YouTube trailer links, awards, and full biographies, making it a complete resource for entertainment-related information.

## API Version

v1 (current)

## Available Endpoints

1. Titles

   ### Titles - Multiples:

   - path: /titles
   - description: returns array of titles according to filters

   ### Titles - By List of Id's:

   - path: /x/titles-by-ids
   - description: returns array of titles according to array of id's provided

   ### Title

   - path: /titles/{id}
   - description: returns title according to filters

   ### Title Rating

   - path: /titles/{id}/ratings
   - description: returns title rating and votes number

2. Search

   ### Titles by Keyword

   - path: /titles/search/keyword/{keyword}
   - description: returns array of titles according to filters

   ### Titles by Title

   - path: /titles/search/title/{title}
   - description: returns array of titles according to filters

   ### Titles by Aka's

   - path: /titles/search/akas/{aka}
   - description: returns array of titles according to filters

3. Actors

   ### Actors

   - path: /actors
   - description: returns array of actors according to filters provided

   ### Actor By Id

   - path: /actors/{id}
   - description: returns actor details

4. Utils

   ### Title Type

   - path: /title/utils/titleType
   - description: returs array of title types

   ### Genres

   - path: /title/utils/titleType
   - description: returs array of genres

   ### Titles Lists

   - path: /title/utils/lists
   - description: returns array of lists (for 'list' query parameter)

   ## Request and Response Format

   Request
   curl --request GET
   --url https://moviesdatabase.p.rapidapi.com/titles/ API KEY/main_actors
   --header 'x-rapidapi-host: moviesdatabase.p.rapidapi.com'
   --header 'x-rapidapi-key: API KEY'

   Response
   {
   "results": []
   }

## Authentication

To access the API, every request must be authenticated using an **API key**. When you register or subscribe to the service, you will be issued a unique key that identifies your account and grants access to the database.

Include this key in the **HTTP headers** of your requests as follows:

```
GET https://api.example.com/movies/12345
Headers:
  Authorization: Bearer YOUR_API_KEY
  Content-Type: application/json
```

Without a valid key, requests are denied. Keep your key secure.

## Error Handling

The API may return errors such as 401 Unauthorized if your API key is missing or invalid, 404 Not Found when a resource does not exist, and 500 Internal Server Error for unexpected server issues. Always check the HTTP status code in the response to determine the type of error. For client-side issues like 401 or 404, verify your request parameters and authentication headers. For server-side errors, implement retries with exponential backoff or log the error for later review. Proper error handling ensures your application remains stable and user-friendly.

## Usage Limits and Best Practices

The API enforces rate limits to ensure fair usage, meaning you can only make a certain number of requests per minute or per day depending on your subscription plan. Exceeding these limits will result in 429 Too Many Requests errors. To use the API effectively, cache frequently accessed data to reduce redundant calls, and batch requests where possible. Implement retries with backoff strategies for transient errors, and always monitor your usage to stay within the allowed quota. Following these practices will help maintain smooth and efficient integration with the API
