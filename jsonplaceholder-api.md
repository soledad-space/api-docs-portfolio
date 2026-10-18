# JSONPlaceholder API: Get a Post

JSONPlaceholder is a free mock API used for testing and practice. When you request a post by its number, the API returns a sample blog post. This lets developers practice fetching data in their apps without setting up a backend server.

## Make a request

Send a request to this address:

```
https://jsonplaceholder.typecode.com/posts/1
```
The `1` at the end is the post number. When you change it to `2`, you get a different post.

## Read the response

The API sends back one post. Here are its values:

- `userId`: The ID number of the user who wrote the post. Example: 1
- `id`: The ID number of the post itself which matches the number in the web address. 
- `title`: The headline of the post (filled with placeholder text).
- `body`: The main paragraph text of the post (also a placeholder text).