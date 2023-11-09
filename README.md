# database_movie

**1. Create a Database called movies.**
```
   use movies

 output :-  test> use movies
            switched to db movies
```
**2.  Create a collection called moviedetails.**
```
   db.createCollection("moviedetails")

  output :-  movies> show collections
             moviedetails
```
**3. Create above 5 movie documents into a moviedetails collection.**
```
   db.moviedetails.insertMany([{movie_title:"Jurassic Park",type:"Adventure",director:"Steven Spielberg",release_year:"1993"},{movie_title:"Forrest Gump",type:"Drama",director:"Robert Zemeckies",release_year:"1994"},{movie_title:"Titanic",type:"Romance",director:"James Cameron",release_year:"1997"},{movie_title:"The Dark Knight",type:"Action",director:"Christopher Nolan",release_year:"2008"},{movie_title:"Avatar",type:"Science Fiction",director:"James Cameron",release_year:"2009"}])
```
**4. List all documents created.**
```
  movies> db.moviedetails.find()
[
  {
    _id: ObjectId("654c820598abff1f9d2db222"),
    movie_title: 'Jurassic Park',
    type: 'Adventure',
    director: 'Steven Spielberg',
    release_year: '1993'
  },
  {
    _id: ObjectId("654c820598abff1f9d2db223"),
    movie_title: 'Forrest Gump',
    type: 'Drama',
    director: 'Robert Zemeckies',
    release_year: '1994'
  },
  {
    _id: ObjectId("654c820598abff1f9d2db224"),
    movie_title: 'Titanic',
    type: 'Romance',
    director: 'James Cameron',
    release_year: '1997'
  },
  {
    _id: ObjectId("654c820598abff1f9d2db225"),
    movie_title: 'The Dark Knight',
    type: 'Action',
    director: 'Christopher Nolan',
    release_year: '2008'
  },
  {
    _id: ObjectId("654c820598abff1f9d2db226"),
    movie_title: 'Avatar',
    type: 'Science Fiction',
    director: 'James Cameron',
    release_year: '2009'
  }
]
```
**5. List James Cameron’s movies.**
```
movies> db.moviedetails.find({director:"James Cameron"},{type:0,release_year:0,_id:0})

output:-
[
  { movie_title: 'Titanic', director: 'James Cameron' },
  { movie_title: 'Avatar', director: 'James Cameron' }
]
```
**6.List  James Cameron’s movies released in 2009.**
```
db.moviedetails.find({release_year:"2009"})

output :- 
{
    _id: ObjectId("654c820598abff1f9d2db226"),
    movie_title: 'Avatar',
    type: 'Science Fiction',
    director: 'James Cameron',
    release_year: '2009'
  }
```
**7. Delete the movie which you don’t like.**
```
db.moviedetails.remove({movie_title:"Titanic"})
```

**8. Add the movie which is your favourite.**
```
db.moviedetails.insertOne({movie_title:"Avengers: Endgame",type:"Action",director:"Russo Brothers",release_year:"2019"})
```

**9. List movie Directed  by Christopher Nolan in 1994.**
```
db.moviedetails.find({release_year:"2009",director:"Christopher Nolan"})

output :- emty
```

**10. List out the Director’s Name in your document. **
```
db.moviedetails.distinct("director")

output : - 
[
  'Christopher Nolan',
  'James Cameron',
  'Robert Zemeckies',
  'Russo Brothers',
  'Steven Spielberg'
]
```
11.

   
