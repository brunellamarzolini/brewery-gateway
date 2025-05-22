# Brewery Gateway

A full-stack project with a Django REST Framework backend that proxies requests to the Open Brewery DB API, and a Vue.js frontend for displaying brewery data.  
The backend validates incoming query parameters and forwards them to the external API, returning the results to the frontend for visualization.

## Features

- Proxy endpoints for brewery lists and metadata
- Query parameter validation using DRF serializers
- Interactive frontend built with Vue.js to display and search brewery data


## Requirements

- [Docker](https://www.docker.com/) installed
- [Docker Compose](https://docs.docker.com/compose/) installed

## Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/brunellamarzolini/brewery-gateway.git
   cd brewery-gateway
   ```

2. **Run Docker:**
   ```bash
   docker compose up
   ```

## Usage

### Endpoints

- **GET `/api/breweries/`**  
  Query the list of breweries.  
  Query parameters are validated by `BreweryListQuerySerializer`.

- **GET `/api/breweries/meta/`**  
  Query brewery metadata.  
  Query parameters are validated by `BreweryMetaQuerySerializer`.

### Example Request

```bash
curl "http://localhost:8000/api/breweries/?page=1&per_page=10&by_country=United+States"
```

## API Documentation

- **Swagger UI:** [http://localhost:8000/api/schema/swagger-ui/](http://localhost:8000/api/schema/swagger-ui/)
