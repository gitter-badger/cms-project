# cms-project
Recreating Wordpress

## features

### users can add/edit/delete a blog post

### people can create accounts to become users

### each user has a homepage with a list of blogposts

### login with custom dialogue box to see admin screen

### user can only add/edit/delete hers or his posts.


## Database setup

Two tables: one user can have many blogposts.

CREATE TABLE users (
  id serial primary key not null,
  name varchar(255) not null,
  password varchar(255) not null
);

CREATE TABLE blogposts (
  id serial primary key not null,
  user_id int not null REFERENCES users(id),
  post text not null,
  created timestamp not null,
  last_edited timestamp not null
);
