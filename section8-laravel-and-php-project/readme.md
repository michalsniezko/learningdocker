## To jest stan projektu po wykonaniu wszystkich czynnosci z komentarza
https://www.udemy.com/course/docker-kubernetes-the-practical-guide/learn/lecture/22167198#questions/18527114

# Build your project (delete any existing "src" directory)
`docker compose run composer create-project --prefer-dist laravel/laravel .`

# Start your project
`docker compose up -d server php mysql`

# Edit your environment variables
```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret
```
# You must run the Artisan migration FIRST
-- the default configuration now uses flatstorage (sqlite), and now we need to migrate the data to our SQL database

`docker compose run artisan migrate`

one more command to update the view's cache

`docker compose run artisan view:cache`

and finally (new with Laravel 12), you MUST generate an encryption key

`docker compose run artisan key:generate`

# You should now be able to view your project at http://localhost:8000
