// Посты

Table posts {
  id integer [primary key]
  author_id integer
  text text
  created_at timestamp
  location point
}

Table posts_photoes {
  path string [primary key]
  post_id integer
}

Table posts_comments {
  id integer [primary key]
  post_id integer
  author_id integer
  text text
}

Table posts_reactions {
  id integer [primary key]
  post_id integer
  author_id interger
  reaction boolean
}


Ref: posts_comments.post_id > posts.id
Ref: posts_reactions.post_id > posts.id
Ref: posts_photoes.post_id > posts.id


// пользователи (описание только для учета подписок)

Table users {
  id integer
  name string
  created_at timestamp
}

Table users_subscriptions { 
  user_id interger
  subscriber_id integer
  created_at timestamp
}

Table users_subscription_count { 
  user_id interger
  subscribes_count integer
  followers_count integer
}

Ref: users.id - users_subscriptions.user_id
Ref: users.id - users_subscriptions.subscriber_id
Ref: users.id - users_subscription_count.user_id