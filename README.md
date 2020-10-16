# App

To start your Phoenix server:

- Install dependencies with `mix deps.get`
- Create and migrate your database with `mix ecto.setup`
- Install Node.js dependencies with `npm install` inside the `assets` directory
- Start Phoenix endpoint with `mix phx.server`

Now you can visit [`localhost:4000`](http://localhost:4000) from your browser.

Ready to run in production? Please [check our deployment guides](https://hexdocs.pm/phoenix/deployment.html).

## Learn more

- Official website: https://www.phoenixframework.org/
- Guides: https://hexdocs.pm/phoenix/overview.html
- Docs: https://hexdocs.pm/phoenix
- Forum: https://elixirforum.com/c/phoenix-forum
- Source: https://github.com/phoenixframework/phoenix

## Steps

https://youtu.be/MZvmYaFkNJI

```
docker-compose run web mix phx.new . --live
```

Change config

```
# Configure your database
config :hello, Hello.Repo,
  username: "postgres",
  password: "postgres",
  database: "hello_dev",
  hostname: "db",
  show_sensitive_data_on_connection_error: true,
  pool_size: 10
```

```
docker-compose run web mix phx.gen.live Timeline Post posts username body likes_count:integer reposts_count:integer
```

Add routes

```
live "/posts", PostLive.Index, :index
live "/posts/new", PostLive.Index, :new
live "/posts/:id/edit", PostLive.Index, :edit

live "/posts/:id", PostLive.Show, :show
live "/posts/:id/show/edit", PostLive.Show, :edit
```

```
docker-compose up
```

To edit database: http://localhost:8080/?pgsql=db&username=postgres&db=hello_dev&ns=public
