# Frontend
##api url : https://api.themoviedb.org/3/movie/76341?api_key=<<api_key>>

##api_key = x3ddxxdxxddxx386xx6afxx3xx73bdxx

👉 Get all the movies

`const requests = {
  fetchTrending: `/trending/all/week?api_key=${API_KEY}&language=en-US`,
  fetchNetflixOriginals: `/discover/tv?api_key=${API_KEY}&with_networks=213`,
  fetchTopRated: `/movie/top_rated?api_key=${API_KEY}&language=en-US`,
  fetchActionMovies: `/discover/movie?api_key=${API_KEY}&with_genres=28`,
  fetchComedyMovies: `/discover/movie?api_key=${API_KEY}&with_genres=35`,
  fetchHorrorMovies: `/discover/movie?api_key=${API_KEY}&with_genres=27`,
  fetchRomanceMovies: `/discover/movie?api_key=${API_KEY}&with_genres=10749`,
  fetchDocumantaries: `/discover/movie?api_key=${API_KEY}&with_genres=99`
}`

`npm i axios`

`👉Build the Rows`

// react hook
 
const [movies,setMovies]=useState([])

👉Build the Banner

👉Build the Youtube Player

👉Build the Model using panda 

👉Build the Apis for getting :
### List of movies
### Recommended movies



