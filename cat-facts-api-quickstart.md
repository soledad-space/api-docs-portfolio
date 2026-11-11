# Cat Facts API: Quickstart

## What is the Cat Facts API

The Cat Facts API is a free service that hands back random facts about cats when you ask. It also returns a list of cat breeds with their countries, origins, and coat details. It's a friendly pick for fun apps, bots, widgets, and learning how to call an API.  

In this guide, you'll learn how to make your first request, read the response, and learn what to do when no fact comes back.

> **Note:** The behavior in this guide was tested in November 2026. The API's own documentation doesn't describe some of it, such as the empty response below 20.

## Before you start

It doesn't require an API key; no authentication or sign-up needed. The base URL (the address that every request starts with) is `https://catfact.ninja`.

## Make your first request

To make your first request: 

1. Go to catfact.ninja and open the docs page.
2. Locate `GET /fact`.
3. Click on `Try it out`.
4. Click on `Execute`.
5. Read the response body — the part of the response that holds the fact. It returns only one fact each time you execute. 

Or paste this URL in your browser: `https://catfact.ninja/fact` 

## Read the response

The response body contains two fields: the `fact` and its `length` — the number of characters in the fact, including spaces. Example: 

```
{
  "fact": "The first commercially cloned pet was a cat named \"Little Nicky.\" He cost his owner $50,000, making him one of the most expensive cats ever.",
  "length": 140
}
```

**Note:** Your fact text will be different because it is random.

## Limit the length of a fact

The `max_length` parameter is an integer that sets the maximum number of characters the returned fact will have. This is optional; it isn't needed to retrieve a fact.

 Use a whole number. If the value is not a number, such as, `abc` the API ignores it and returns a random fact. Values below 20 return an empty response. The smallest value that works is 20.


Example request: `https://catfact.ninja/fact?max_length=20`. This request returns:

```
{
  "fact": "Cats have 3 eyelids.",
  "length": 20
}
```

## Handle empty results

If no fact fits your `max_length`, the API will still return a status code `200` (a code that tells you the request was successful), but the response body will be empty: 

```
{}
```

For example, `https://catfact.ninja/fact?max_length=10` returns `{}`

The API documentation lists a `404` response with the text "Fact not found", but a `max_length` value that is too small doesn't return it. Check that the `fact` field is in the response before using it. Don't wait for a `404` response.

## Other endpoints

### Get a list of facts

`GET /facts` returns a list of facts, not just one.

- `limit`: This allows you to specify the number of facts that will be returned. It is optional; if you leave it out, the API returns 10 facts.
- `max_length`: Sets the maximum number of characters in each fact, as in `GET /fact`

Example request: `https://catfact.ninja/facts?limit=5`

### Get a list of breeds

`GET /breeds` returns a list of cat breeds with their countries, origins, coat details, and patterns.

- `limit`: Sets the number of breeds to return, as in `GET /facts`. It is also optional; the API returns 25 breeds if you leave it out.

Example request: `https://catfact.ninja/breeds?limit=3`

The response has one record for each breed. Here is one:

```
    {
      "breed": "Abyssinian",
      "country": "Ethiopia",
      "origin": "Natural/Standard",
      "coat": "Short",
      "pattern": "Ticked"
    }
```

- `breed`: the name of the cat breed.
- `country`: the country linked to the breed.
- `origin`: how the breed came about.
- `coat`: the length of the coat.
- `pattern`: the pattern of the coat.
