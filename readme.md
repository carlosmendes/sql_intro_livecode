## 1. Model the following context, an ecommerce portal, in db.lewagon.org
# A client can register using is email and password
# The portal contains several products described by name and price
# A client can make several orders
# Each order belongs to a client, has one deliver address and date and several products

## 2. Define Queries for these questions

# the list of artists with albums title including the word 'hits', ordered by artist name.
SELECT artists.name, albums.title
FROM artists
  JOIN albums ON (albums.artist_id = artists.id)
WHERE albums.title LIKE '%hits%'
ORDER BY artists.name

# list of top 5 artists (names) with more albums
SELECT artists.name, count(albums.id) as albums_count
FROM albums JOIN artists ON (albums.artist_id = artists.id)
GROUP BY artists.name
ORDER BY albums_count DESC
LIMIT 5

# list of top 5 artists (names) with more genres - Check DISTINCT
SELECT artists.name, count(DISTINCT tracks.genre_id) as genres_count
FROM albums JOIN artists ON (albums.artist_id = artists.id)
  JOIN tracks ON (tracks.album_id = albums.id)
GROUP BY artists.name
ORDER BY genres_count DESC
LIMIT 5

# avg number of tracks per album
-- SUM(tracks) / COUNT(tracks)

# list of artists (id and name) that do not have any album - Check NOT IN or LEFT JOIN


# list of albums (title) that have average song length > 180s - Check HAVING


# list of artists that have tracks of all genres - Check NOT EXISTS



