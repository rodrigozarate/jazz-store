# jazz-store
## Basics RESTful web service API with Go and Gin
## API endpoints
    GET – Get a list of all albums, returned as JSON.

    POST – Add a new album from request data sent as JSON.

/albums/:id

    GET – Get an album by its ID, returning the album data as JSON.
## STRUCT
type album struct {
        ID     string  `json:"id"`
        Title  string  `json:"title"`
        Artist string  `json:"artist"`
        Price  float64 `json:"price"`
}
## SLICE
var albums = []album{
        {ID: "1", Title: "Blue Train", Artist: "John Coltrane", Price: 56.99},
        {ID: "2", Title: "Jeru", Artist: "Gerry Mulligan", Price: 17.99},
        {ID: "3", Title: "Sarah Vaughan and Clifford Brown", Artist: "Sarah Vaughan", Price: 39.99},
}
## EXAMPLE
### Get all albums
curl http://localhost:8080/albums --header "Content-Type: application/json" --request "GET"

### Post one new album
curl http://localhost:8080/albums --include --header "Content-Type: application/json" --request "POST" --data '{"id": "4","title": "The Modern Sound of Betty Carter","artist": "Betty Carter","price": 49.99}'


