## 📽️ MoviesDatabase API Overview
The MoviesDatabase API provides access to a massive collection of over 9 million movies, series, and episodes, along with detailed data on 11 million actors and crew members. It includes metadata such as ratings, genres, trailers, awards, biographies, and more. This makes it ideal for building movie discovery platforms like CineSeek.

## 🔗 Available Endpoints

/titles	: Returns a list of titles with optional filters like year, genre, and sorting
/titles/{id} : Fetches detailed information about a specific title by IMDb ID
/titles/{id}/ratings : Retrieves ratings and vote count for a title
/titles/x/upcoming : Lists upcoming titles
/titles/search/title/{title} : Searches titles by name
/titles/search/keyword/{keyword} : Searches titles using keywords
/actors : Lists actors with optional filters
/actors/{id} : Retrieves detailed information about a specific actor
/title/utils/genres : Returns available genres
/title/utils/titleType : Returns available title types

## 📬 Request and Response Format

Example Request (GET /titles)
GET https://moviesdatabase.p.rapidapi.com/titles?year=2024&genre=Comedy&page=1
Headers:
  x-rapidapi-host: moviesdatabase.p.rapidapi.com
  x-rapidapi-key: YOUR_API_KEY


  Example Response
json
{
  "results": [
    {
      "id": "tt1234567",
      "titleText": { "text": "Example Movie" },
      "primaryImage": { "url": "https://image.url" },
      "releaseYear": { "year": 2024 },
      "genres": { "genres": ["Comedy"] }
    }
  ],
  "page": 1,
  "next": 2,
  "entries": 12
}

## 🔐 Authentication

To authenticate your requests:

Use an API key from RapidAPI.

Include these headers:

x-rapidapi-host: moviesdatabase.p.rapidapi.com
x-rapidapi-key: YOUR_API_KEY
Store your API key securely in .env.local:

MOVIE_API_KEY=your_api_key_here

## ⚠️ Error Handling
Common error responses:

401 Unauthorized: Invalid or missing API key

404 Not Found: Invalid endpoint or resource ID

429 Too Many Requests: Rate limit exceeded

500 Internal Server Error: Server-side issue

Use try/catch blocks and check response.ok to handle errors gracefully.

## 📊 Usage Limits and Best Practices

Rate Limits: Respect request limits to avoid throttling

Pagination: Use limit and page to manage large datasets

Caching: Cache frequent responses to reduce load

Environment Variables: Store sensitive data securely

Error Boundaries: Implement UI-level error handling for better UX