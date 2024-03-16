# Deploying Fake Back-End Server & DataBase Using JSON-SERVER, GitHub, and Heroku.

In this article, we will create and host a fake server that we can deal with it as a normal Back-End Server and use all the CRUD Operations using HTTP requests.

# 1.Creating the Fake Server.

- Create a folder and name it `fake-server`.
- Open the terminal and init npm, and make the entry point `server.js`

```
npm init
```

- install [json-server](https://www.npmjs.com/package/json-server).

```
npm i json-server
```

- Add a `start` script.

package.json

```
{
  "name": "fake-server",
  "version": "1.0.0",
  "description": "fake server with fake database",
  "main": "server.js",
  "scripts": {  // <===
    "start": "node server.js" // <===
  },
  "author": "Author Name",
  "license": "ISC",
  "dependencies": {
    "json-server": "version"
  }
}
```

- create `.gitignore` file and add `node_modules`.
  .gitignore

```bash
node_modules
```

- Create `server.js` file and paste the following

```js
const jsonServer = require("json-server");
const server = jsonServer.create();
const router = jsonServer.router("db.json"); // <== Will be created later
const middlewares = jsonServer.defaults();
const port = process.env.PORT || 3200; // <== You can change the port

server.use(middlewares);
server.use(router);

server.listen(port);
```

- init git and publish your repo to [GitHub](https://github.com/)

```bas
git init
git remote add origin https://github.com/<YourName>/<Repo-Name>.git
git add .
git push --set-upstream origin master
```

> Download the final Repo from [HERE](https://github.com/YoussefZidan/fake-server)

# 2. Creating the DataBase

- Create `db.json` file
- Fill in any data you like, I use [Mockaroo](https://www.mockaroo.com/) to generate dummy data.

db.json

```json
{
  "users": [
    {
      "id": 1,
      "first_name": "Justina",
      "last_name": "Ginglell",
      "email": "jginglell0@networkadvertising.org",
      "gender": "Female"
    },
    {
      "id": 2,
      "first_name": "Marion",
      "last_name": "Jenman",
      "email": "mjenman1@surveymonkey.com",
      "gender": "Male"
    },
    {
      "id": 3,
      "first_name": "Alfy",
      "last_name": "Begin",
      "email": "abegin2@list-manage.com",
      "gender": "Female"
    },
    {
      "id": 4,
      "first_name": "Karney",
      "last_name": "Zanussii",
      "email": "kzanussii3@hao123.com",
      "gender": "Male"
    },
    {
      "id": 5,
      "first_name": "Reid",
      "last_name": "Schapero",
      "email": "rschapero4@timesonline.co.uk",
      "gender": "Male"
    },
    {
      "id": 6,
      "first_name": "Dorine",
      "last_name": "Braybrookes",
      "email": "dbraybrookes5@gov.uk",
      "gender": "Female"
    },
    {
      "id": 7,
      "first_name": "Sarena",
      "last_name": "Frape",
      "email": "sfrape6@alexa.com",
      "gender": "Female"
    },
    {
      "id": 8,
      "first_name": "Malva",
      "last_name": "Pierse",
      "email": "mpierse7@usda.gov",
      "gender": "Female"
    },
    {
      "id": 9,
      "first_name": "Rania",
      "last_name": "Dablin",
      "email": "rdablin8@state.gov",
      "gender": "Female"
    },
    {
      "id": 10,
      "first_name": "Ingrim",
      "last_name": "Offen",
      "email": "ioffen9@slideshare.net",
      "gender": "Male"
    }
  ]
}

{
      "id": 1,
      "firstName": "Anthony",
      "middleName": "M",
      "lastName": "suresh",
      "gender": "Male",
      "email": "manthonysuresh@gmail.com",
      "mobile": "9943567950",
      "dob": "1995-05-28",
      "address": "363,  south street, Elayankanni, Tiruvannamalai, Tamil Nadu- 606753",
      "cob": "India",
      "active": true
    }
```

- Push your work

```bash
git add .
git commit -m "creating the database"
git push
```


Now, You can access and modify resources via any HTTP method
`GET` `POST` `PUT` `PATCH` `DELETE` `OPTIONS`

