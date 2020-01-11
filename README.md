# README

Adopted from https://scotch.io/tutorials/build-a-restful-json-api-with-rails-5-part-one

Ran these `rails` commands:
```
$ rails new todos-api --api -T
$ rails g rspec:install
$ rails g model Todo title:string created_by:string
$ rails g model Item name:string done:boolean todo:references
$ rails db:migrate
$ rails g controller Todos
$ rails g controller Items
$ rails routes
$ rails s
```

Execute RSpec tests:
```
$ bundle exec rspec
```

Test REST APIs:
```
# GET /todos
$ http :3000/todos

# POST /todos
$ http POST :3000/todos title=Swim-1 created_by=1

# PUT /todos/:id
$ http PUT :3000/todos/1 title=Swim-2

# DELETE /todos/:id
$ http DELETE :3000/todos/1
```

```
# GET /todos/:todo_id/items
$ http :3000/todos/1/items

# POST /todos/:todo_id/items
$ http POST :3000/todos/1/items name='49ers' done=false

# PUT /todos/:todo_id/items/:id
$ http PUT :3000/todos/1/items/1 done=true

# DELETE /todos/:todo_id/items/1
$ http DELETE :3000/todos/1/items/1
```