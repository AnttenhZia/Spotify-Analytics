# For this project, I downloaded Spotify data from Kaggle.
# Then I created a table to insert Spotify data into.
# Finally, I performed analytics on the data using SQL. 

#Creating the table: 
CREATE TABLE BIT_DB.Spotifydata (
id integer PRIMARY KEY,
artist_name varchar NOT NULL,
track_name varchar NOT NULL,
track_id varchar NOT NULL,
popularity integer NOT NULL,
danceability decimal(4,3) NOT NULL,
energy decimal(4,3) NOT NULL,
key integer NOT NULL,
loudness decimal(5,3) NOT NULL,
mode integer NOT NULL,
speechiness decimal(5,4) NOT NULL,
acousticness decimal(6,5) NOT NULL,
instrumentalness text NOT NULL,
liveness decimal(5,4) NOT NULL,
valence decimal(4,3) NOT NULL,
tempo decimal(6,3) NOT NULL,
duration_ms integer NOT NULL,
time_signature integer NOT NULL 
)

#Then I inserted the Spotify Data .csv into the table.

#Next, I explored the data using the following SQL. 

-- Fetch artist name and popularity sorted by the popularity column in the ASCending order:

SELECT artist_name, popularity, track_name
FROM BIT_DB.Spotifydata
ORDER BY popularity desc LIMIT 10;

--Fetch artist names that have a popularity above 94

SELECT artist_name
FROM BIT_DB.Spotifydata
WHERE popularity > 94;

---Fetch the avg popularity, danceability, and energy by artist and track

SELECT artist_name, track_name, avg(popularity), avg(danceability), avg(energy)
FROM BIT_DB.spotifydata
GROUP BY artist_name, track_name;
