# Getting started with Starflix

## Get your API key

Starflix uses an API from The Movie Database (**TMDB**) to fetch data of movies and TV shows from their website. You'll need to register at TMDB's website to get your own API key.

To get your API key, follow the steps described in [TMDB's official documentation](https://developers.themoviedb.org/3/getting-started/introduction "TMDB documentation website").

## Edit **secrets.js** with your API key

Go to the **/src** directory and edit the [secrets.js](./src/secrets.js) file. Replace *YOUR_API_KEY* with your own key provided by TMDB.

```java
const API_KEY="YOUR_API_KEY"; // Replace YOUR_API_KEY with the key from TMDB (sample key: 13dxxxxxcddc83xxx06af363b173xxxx)
const BASE_URL="http://localhost:8000";

export { BASE_URL };

export default API_KEY;
```

## Run the application

Open your cmd prompt and navigate to the project's root directory

Run the command "npm install" to install all the necessary dependencies, and wait for it to finish.

Then, run the command "npm start" to start the development version of the application on port 3000.

If the application does not show up in a new browser tab, navigate to your browser window (or open a new one), and type the following into the address bar: localhost:3000

Any updates made to the application code, will automatically show up when the localhost page is refreshed.
## Frontend

### API base URL

> `https://api.themoviedb.org/3/movie/76341?api_key=<api_key>`

Remember to replace *<api_key>* with your own key provided by TMDB (sample key: 13dxxxxxcddc83xxx06af363b173xxxx).

### Endpoints

This section will provide you with code samples for TMDB's endpoints used by Starflix.

To see the full documentation for each endpoint, refer to [TMDB's official website](https://developers.themoviedb.org/3/getting-started/introduction "TMDB documentation website").

#### 👉 Get all the movies and TV shows

```java
  const requests = {
    fetchTrending: `/trending/all/week?api_key=${API_KEY}&language=en-US`, // Get the list of trending movies, TV shows and people in the current week. 
    fetchNetflixOriginals: `/discover/tv?api_key=${API_KEY}&with_networks=213`, // Get the list of Netflix Originals.
    fetchTopRated: `/movie/top_rated?api_key=${API_KEY}&language=en-US`, // Get the list of top rated movies.
    fetchActionMovies: `/discover/movie?api_key=${API_KEY}&with_genres=28`, // Get the list of movies by genre (Action).
    fetchComedyMovies: `/discover/movie?api_key=${API_KEY}&with_genres=35`, // Get the list of movies by genre (Comedy).
    fetchHorrorMovies: `/discover/movie?api_key=${API_KEY}&with_genres=27`, // Get the list of movies by genre (Horror).
    fetchRomanceMovies: `/discover/movie?api_key=${API_KEY}&with_genres=10749`, // Get the list of movies by genre (Romance).
    fetchDocumantaries: `/discover/movie?api_key=${API_KEY}&with_genres=99` // Get the list of movies by genre (Documentaries).
}
```

#### 👉 Build the Rows

Each of the category rows are created from the same row component. Each row has a series of show/movie titles as well as a row title. The series of titles are rendered by iterating over the list of movies and creating a new movie component for each title.

```
  return (
    <div className='row'>
        {/* title */}
        <h2 className='title' >{title}</h2>

        <div className='row-posters' >
          {/* several row posters */}
          {movies.map((movie,i)=>{
            return <div className='row_div'>
                <img key={i} className="row_poster" src={base_url+movie.poster_path} onClick={()=>handleClick(movie)} alt={movie.name} ></img>
                <p className='row_div_rating'>{(movie.vote_average.toFixed(1))}</p>
              </div>
          })}

        </div>
        {trailerUrl && <YouTube videoId={trailerUrl} className="youtube" opts={opts}></YouTube>}
        {/*Container-> images */}

    </div>
  )
```

#### 👉 Build the Banner

*Under construction...*

#### 👉 Build the Youtube Player

*Under construction...*

## Backend

### 👉 Get the databases from Kaggle

> `https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata?select=tmdb_5000_movies.csv`

### 👉 Build the Model

```npm install```

### 👉 Build the APIs for getting:

* List of movies
* Recommended movies
