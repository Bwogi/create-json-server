# Create your own JSON server
## Create a package.json file
```
npm init -y
``` 

## Download the server package
`npm i json-server`

## Create a script that connects the server to your database file
* change the server port from 3000 to 5000 because react also uses 3000 by default
```json
"scripts":{
 "server": "json-server --watch db.json --port 5000"
}
```

## Add the data
```
touch db.json
```
## Create 2 collections: posts and users
```json
{
 "posts":[],
 "users":[]
}
```
## Populate them(3 posts and 1 user)
```json
{
 "posts":[
   {
      "id": "1",
      "title": "Title One",
      "body": "This is the body",
      "publishedAt": "11-01-2021"
   },
    {
    "id": "2",
    "title": "Title Two",
    "body": "This is the body",
    "publishedAt": "11-01-2021"
    },
     {
       "id": "3",
       "title": "Title Three",
       "body": "This is the body",
       "publishedAt": "11-01-2021"
    }
 ],
 "users":[
   {
     "id": "1",
     "name":"Bwogi Andrew",
     "email":"bwogi@andrew.com"
   }
 ]
}
```
## Run the Server
```
npm run server
```

## Go to postman or insomnia
### Viewing/ Fetching data
```
GET http://localhost:5000/posts
```
will return all the (3) posts from the database
```
GET http://localhost:5000/users
```
will return all the (1) user(s) from the database
### Creating/ posting records
```
POST http://localhost:5000/posts
```
* select the `body` tab
* select `raw`
* select `JSON` instead of `Text` to select `JSON Data`
* don't add an id for the post.
```json
{
  "title": "Title Four",
  "body": "This is the body"
  "publishedAt": "11-02-2021"
}
```
hit `send`
### Result
`it has returns the new record with an id`
### Check the db.json file
`the new record is in the database file`

