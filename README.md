try-cb-golang
===============

A sample application and dataset for getting started with Couchbase 4.5 or later.  The application runs a single page
UI for demonstrating query capabilities.   The application uses Couchbase Server +  Node.js + Express + Angular and
boostrap.   The application is a flight planner that allows the user to search for and select a flight route (including
return flight) based on airports and dates. Airport selection is done dynamically using an angular typeahead bound to cb
server query.   Date selection uses date time pickers and then searches for applicable air flight routes from a
previously populated database.  You additionally can use Full-Text Search to perform hotel searches.

## Installation and Configuration
The steps below assume you are running a standalone couchbase instance running kv, indexing, fts (in Couchbase 4.5 or
later) and query services on the same server where the node application will also be running.

 1. Install a Couchbase Server, start it, and load the `travel-sample` bucket.
    * If you want to use Full-Text Search, set up an FTS index called `hotels` for all documents of type `hotel`

 2. Run the included `create-collections.sh` script to set up the correct collections
 ```bash
 ./create-collections.sh Adminstrator password localhost
 ```
 3. Install Go 1.6+

 4. Make a GOPATH directory and then use `go get` to fetch this repo.  From a terminal:

 ```bash
 go get -u "github.com/couchbaselabs/try-cb-golang"
 ```

 5. Start the application. From a terminal:

 ```bash
 cd src/github.com/couchbaselabs/try-cb-golang/
 go run main.go
 ```

 6. Open a browser and load the url http://localhost:8080

## REST API DOCUMENTATION
The REST API for this example application can be found at:
[https://github.com/couchbaselabs/try-cb-frontend/blob/master/documentation/try-cb-api-spec-v2.adoc](https://github.com/couchbaselabs/try-cb-frontend/blob/master/documentation/try-cb-api-spec-v2.adoc)
