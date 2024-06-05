## API Usage

### Create Article


```powershell
Invoke-RestMethod -Uri "http://127.0.0.1:5000/v1/articles/" -Method Post -ContentType "application/json" -Body '{"tags": ["example", "demo"]}'
```

Expected Response:

    HTTP 200 OK with the article details.
    A Location header indicating the URL of the new article.

Retrieve Article

To retrieve an article by its ID, replace <ARTICLE_ID> with the actual ID of the article:

```powershell

Invoke-RestMethod -Uri "http://127.0.0.1:5000/v1/articles/<ARTICLE_ID>"
```
Expected Response:

    HTTP 200 OK with the article JSON data if found.
    HTTP 404 Not Found if the article does not exist.

Add Tags to Article

To add tags to an existing article, replace <ARTICLE_ID> with the ID of the article you wish to update, and use the following command:

```powershell

Invoke-RestMethod -Uri "http://127.0.0.1:5000/v1/articles/<ARTICLE_ID>/tags" -Method Post -ContentType "application/json" -Body '{"tags": ["new", "tags"]}'
```
Expected Response:

    HTTP 200 OK with the updated article details.
    HTTP 404 Not Found if the article does not exist.
    HTTP 400 Bad Request if there is an issue with the input data.



