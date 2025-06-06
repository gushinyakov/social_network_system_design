// Известыне локации для поиска, которые можно маппить к постам

Table popular_places {
  id integer [primary key]
  name string
  location point
}


Table popular_places_post {
  place_id integer [primary key]
  post_id integer[] [primary key]
}

Ref: popular_places.id < popular_places_post.place_id
