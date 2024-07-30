# Boot.dev Web Server

This is a Go-based web server application that provides various API endpoints and serves static files.

## Features

- File serving
- User authentication (login, refresh, revoke)
- User management (create, update)
- Chirp functionality (create, retrieve, delete)
- Webhook handling for Polka integration
- Health check endpoint
- Metrics tracking

## Setup

1. Ensure you have Go installed on your system.
2. Clone this repository.
3. Create a `.env` file in the root directory with the following variables.
4. Run `go mod tidy` to ensure all dependencies are installed.

## Running the Server

To start the server, run:
`go run main.go`
The server will start on port 8080 by default.

To run in debug mode (which resets the database):

## API Endpoints

- `GET /api/healthz`: Health check
- `GET /api/reset`: Reset endpoint
- `POST /api/polka/webhooks`: Webhook handler for Polka
- `POST /api/revoke`: Revoke authentication
- `POST /api/refresh`: Refresh authentication
- `POST /api/login`: User login
- `POST /api/users`: Create user
- `PUT /api/users`: Update user
- `DELETE /api/chirps/{chirpID}`: Delete a chirp
- `POST /api/chirps`: Create a chirp
- `GET /api/chirps`: Retrieve chirps
- `GET /api/chirps/{chirpID}`: Get a specific chirp
- `GET /admin/metrics`: View server metrics

## Static File Serving

Static files are served from the `/app` route. The server looks for files in the current directory.

## Database

The application uses a JSON file (`database.json`) as its database.

## Dependencies

- github.com/joho/godotenv: For loading environment variables
- boot.dev-webserver/internal/database: Custom package for database operations

## Note

Ensure that the `JWT_SECRET` and `POLKA_KEY` environment variables are set before running the server.


