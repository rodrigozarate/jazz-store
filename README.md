# jazz-store
## Basics RESTful web service API with Go and Gin
You can use this code to understand the basic prnciples of routing a web API using GO and GIN

The code will allow the user to interact with data in a slice to:
	List all data
	Get the details of one record
	Add new data to the slice
## INSTALLATION
You can get GO for mac from here: ![GO](https://go.dev/doc/install)
Using your Terminal after installation check you version by typing ´´´$ go version´´´

Download the code and unzip

## USAGE

Type ´´´´$ go run main.go´´´
That should start gin server over port 8080

The file go.mod contains the external modules required to run the app

## API endpoints
/albums
    GET – Get a list of all albums, returned as JSON.

/albums
    POST – Add a new album from request data sent as JSON.

/albums/:id
    GET – Get an album by its ID, returning the album data as JSON.

## STRUCT
Each album has four data fields that must be filled 
```go
type album struct {
        ID     string  `json:"id"`
        Title  string  `json:"title"`
        Artist string  `json:"artist"`
        Price  float64 `json:"price"`
}
```
## SLICE
This is the seed info in the slide
```go
var albums = []album{
        {ID: "1", Title: "Blue Train", Artist: "John Coltrane", Price: 56.99},
        {ID: "2", Title: "Jeru", Artist: "Gerry Mulligan", Price: 17.99},
        {ID: "3", Title: "Sarah Vaughan and Clifford Brown", Artist: "Sarah Vaughan", Price: 39.99},
}
```
## EXAMPLES
### Get all albums
```
curl http://localhost:8080/albums --header "Content-Type: application/json" --request "GET"
```
Or using the browser
http://localhost:8080/albums

### Post one new album
```
curl http://localhost:8080/albums --include --header "Content-Type: application/json" --request "POST" --data '{"id": "4","title": "The Modern Sound of Betty Carter","artist": "Betty Carter","price": 49.99}'
```

