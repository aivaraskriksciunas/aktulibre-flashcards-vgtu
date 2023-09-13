# Aktulibre

## Setup
Download the github repository.

 1. Download the github repository
 2. In flashcards/ folder copy and rename *.example files by removing the .example part
 3. Make sure that in your .env file database connection info is correct
 4. Run `docker-compose up`
 5. Go to the php container by executing `docker exec -it <container_id> /bin/sh`
 6. In the container, setup the database by executing  `php artisan migrate` and `php artisan db:seed --class InitialSeeder`
 7. Go to `localhost:8000` in your browser
 8. Profit!

For the frontend project, it is not being executed on docker for simplicity.

 1. Go to flashcards-front
 2. Run `npm install`
 3. Now, to launch the project run `npm run dev`
 4. To build the project for production, run `npm run build`

You will likely run into issues during this process, so good luck lol.
