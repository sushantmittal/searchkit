# Using Express
`Searchkit` ships with an express plugin to proxy api calls to ElasticSearch

## Installation

```sh
npm install searchkit-express --save
```

```js
SearchkitExpress = require("searchkit-express")
```

```js
var app = express()
//...

SearchkitExpress({
  host:process.env.ELASTIC_URL || "http://localhost:9200",
  log: 'debug',
  index:'movies',
  queryProcessor:function(query, req, res){
    //do neccessery permissions, prefilters to query object
    //then return it
    return query
  }
 }, app)
 ```
 
 This will add the following endpoints to your root url which will route to the `movies` index on your elasticsearch instance
 * POST /_search
 * POST /_msearch
 

 
 