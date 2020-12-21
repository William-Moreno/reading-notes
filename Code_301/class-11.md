# EJS
---
## EJS

**EJS** is a templeting language or engine that we can use to generate HTML with plain JavaScript. EJS stands for Embedded JavaScript. It is most useful when we have to output when we are dealing with real-time updates or generating dynamic contents.

Even though there are a number of options to use for these kinds of processes, EJS is popular because it is relatively esy to set up and its syntax and logic is simple.

To use EJS, we must first install it in our project folder as follows:

```
npm install ejs --save
```

### Intro to EJS

The following notes were drawn from the video series [*"Intro to EJS in ExpressJS"*](https://www.youtube.com/playlist?list=PL7sCSgsRZ-slYARh3YJIqPGZqtGVqZRGt) by *WalkThroughCode*.

#### Getting Started

After installing ejs in our project folder we need to create a folder named *views* and a file named *index.ejs*.

In our server.js we need to add lines to `require('body-parser');` and `require('path');` We also ne to add the following code:
- `app.use('body-parser');`
- `app.set('views', path.join(_dirname, 'views'));`
- `app.set('view engine', 'ejs');`
- `app.get('/', function(req,res) {res.render('index');
});`
- `app.listen(8000, function() { console.log('heard on 8000');
});`

#### Injecting and Evaulating Variables

Variables can be inserted into EJS templates and evaluated as well. to evaluate the variables we must remember to include the `=` character in the EJS tags. For instance:
```
<%= foo %>
```

#### For Loops and Arrays

We can use a line in our server.js to loop through arrays in out EJS template file to generate viewable content:
```JavaScript
res.render('index', { people: [ {name: bob}, {name: sam}]});
```

...and, inside our index.ejs, we include this code:
```
<ul>
  <% for(var person of people) { %>
  <li><%= person.name %></li>
  <% } %>
```

#### If/Else

In the same basic manner, we can include if/else statements in our EJS. Care must be taken to be sure we include the evaluate character `=`, if we need the actual value of a variable in our EJS.

## Google Books API Docs

### Volumes Search

The basic volume search requires a single parameter, `q`, which designates a string to search in volumes for. A basic search string then, would be:

```
https://www.googleapis.com/books/v1/volumes?q=search+terms
```
We can specify special keywords in the search terms in order to search within certain fields:


| **Keywords** | **Descriptions** |
| --- | --- |
| `intitle` | Returns results where the text following the keyword is found in the title |
| `inauthor` | Returns results where the text following the keyword is found in the author |
| `inpublisher` | Returns results where the text following the keyword is found in the publisher |
| `subject` | Returns results where the text following the keyword is found in the publisher |
| `isbn` | Returns results where the text following the keyword matches the ISBN number |
| `lccn` | Returns results where the text following the keyword matches the Library of Congress Control Number |
| `oclc` | Returns results where the text following the keyword matches the Online Computer Library Center number |

**Requests**

An example search using these keywords might be:

```
GET https://www.googleapis.com/books/v1/volumes?q=flowers+inauthor:keyes$key=yourAPIKey
```

**Responses**

A successful response will generate a responser containing a `200 OK` status code as well as the volume results:

```
200 OK

{
 "kind": "books#volumes",
 "items": [
  {
   "kind": "books#volume",
   "id": "_ojXNuzgHRcC",
   "etag": "OTD2tB19qn4",
   "selfLink": "https://www.googleapis.com/books/v1/volumes/_ojXNuzgHRcC",
   "volumeInfo": {
    "title": "Flowers",
    "authors": [
     "Vijaya Khisty Bodach"
    ],
   ...
  },
  {
   "kind": "books#volume",
   "id": "RJxWIQOvoZUC",
   "etag": "NsxMT6kCCVs",
   "selfLink": "https://www.googleapis.com/books/v1/volumes/RJxWIQOvoZUC",
   "volumeInfo": {
    "title": "Flowers",
    "authors": [
     "Gail Saunders-Smith"
    ],
    ...
  },
  {
   "kind": "books#volume",
   "id": "zaRoX10_UsMC",
   "etag": "pm1sLMgKfMA",
   "selfLink": "https://www.googleapis.com/books/v1/volumes/zaRoX10_UsMC",
   "volumeInfo": {
    "title": "Flowers",
    "authors": [
     "Paul McEvoy"
    ],
    ...
  },
  "totalItems": 3
}
```

### Optional Query Parameters

We can use the following query parameters in addition to standard query parameters when performing a volumes search:

**Download Format**

| **Keyword** | **Description** |
| --- | --- |
| `download` | Restrict returned results to volumes that have an available `epub` download format |

*Example*
```
GET https://www.googleapis.com/books/v1/volumes?q=pride+prejudice&download=epub&key=yourAPIKey
```

**Filtering**

Use the `filter` parameter to further restrict returned results:

| **Values** | **Descriptions** |
| --- | --- |
| `partial` | Returns results where parts of the text are previewable |
| `full` | Returns only results where all text is available |
| `free-ebooks` | Returns only results that are free Google eBooks |
| `paid-ebooks` | Returns only results that are priced Google eBooks |
| `ebooks` | Returns only results that are either free or priced Google eBooks, but not magazines or non-eBooks |

*Example*
```
GET https://www.googleapis.com/books/v1/volumes?q=flowers&filter=free-ebooks&key=yourAPIKey
```

**Pagination**

Use the these parameters to paginate volumes" returned results:

| **Keywords** | **Descriptions** |
| --- | --- |
| `startIndex` | position in collection to start from. Like an array, the first item index is 0. |
| `maxResults` | Maximum number of results to return. *Default = 10, maximum allowable = 40.* |

**Print Type**

Set the `printType` parameter to further restrict returned results by publication type of specific print:

| **Values** | **Descriptions** |
| --- | --- |
| `all` | No restriction to type |
| `books` | Returns only books |
| `magazines` | Returns only magazines |

*Example*
```
GET https://www.googleapis.com/books/v1/volumes?q=time&printType=magazines&key=yourAPIKey
```

**Projection**

Set the `projection` parameter to specify a predefined set of Volume fields to return:

| **Values** | **Descriptions** |
| --- | --- |
| `full` | Returns all Volume fields |
| `lite` | Returns only certain fields as designated by double asterisks in the ***Volume refference*** |


*Example*
```
GET https://www.googleapis.com/books/v1/volumes?q=flowers&projection=lite&key=yourAPIKey
```

**Sorting**

Set the `orderBy` parameter to defined set alter the way results are displayed:

| **Values** | **Descriptions** |
| --- | --- |
| `relevance` | Sorts in order of the relevance of the search terms *(default) |
| `newest` | Sorts in order of most recently to least recently published |


*Example*
```
GET https://www.googleapis.com/books/v1/volumes?q=flowers&orderBy=newest&key=yourAPIKey
```

### Retrieving a Specific Volume

We can retrieve a specific volume with a HTTP `GET` request to the Volume resource URL:

```
GET https://www.googleapis.com/books/v1/volumes/zyTCA1FPjgYC?key=yourAPIKey
```

The `accessInfo` section of the returned data is of particular interest when determining what features are available. And, when retreiving by Volume, we can use all of the optional query parameters to control the returned result.

[Back to Main](../README.md)
