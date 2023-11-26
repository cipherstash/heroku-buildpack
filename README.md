<img src="tandem.svg" alt="Ramhorns logo" width="250" align="right">

# Heroku Buildpack for CipherStash Tandem

Deploy [Tandem](https://cipherstash.com/products/tandem) to Heroku with this Buildpack.
It adds the `tandem` binary which can be run as a worker process.

## Deploy to existing app

If you have an existing app in Heroku, you can add this buildpack:

```
heroku buildpacks:add https://github.com/cipherstash/heroku-buildpack
```

This will add this buildpack to your app, alongside any others you might already have.

To start Tandem, you must add an entry to your `Procfile`.
See the [Heroku docs](https://devcenter.heroku.com/articles/procfile) for more info.

```sh
# Existing web worker (example)
web: bundle exec rails server -p $PORT
# Add this line
worker: tandem
```

Commit the change to your Procfile and push to Heroku.

```sh
git add Procfile
git commit -m "Added tandem worker to Heroku Procfile"
git push heroku main
```

