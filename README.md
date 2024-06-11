# Recipe Manager

A basic webpage made for hobby cooking enthusiasts. Users can see, upload, and delete recipes.

## Prerequisites

- Docker

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/JanKastelic1/NUKS_PROJEKT.git
    ```
2. Unzip the downloaded file:
    ```sh
    unzip NUKS_PROJEKT.zip
    ```
3. Build the Docker image:
    ```sh
    docker build -t recipe-manager -f Kit.dockerfile .
    ```
4. Run the Docker container:
    ```sh
    docker run -p 8000:8000 recipe-manager
    ```

## Usage

Open your browser and go to [http://localhost:8000](http://localhost:8000) to use the website.

## Project Structure

All the project files are located in the `NUKS/` folder:

- **API.py**: Contains the server code to handle HTTP requests for viewing, adding, and deleting recipes.
- **background.jpg**: An image used as the background of the webpage.
- **database_init.py**: A script to initialize the SQLite database with the necessary schema.
- **FR.css**: The stylesheet for the webpage.
- **FR.HTML**: The HTML file that serves as the main page of the website.
- **Kit.dockerfile**: Dockerfile used to build the Docker image.
- **recipes.db**: SQLite database file where the recipes are stored.
- **requirements.txt**: Contains a list of Python packages required to run the project.

## API Description

### `do_GET(self)`

Handles GET requests:
- **/**: Serves the main webpage (`FR.html`).
- **/static/**: Serves static files such as CSS and images.
- **/recipes**: Returns a list of all recipes in JSON format.

### `serve_index(self)`

Serves the main webpage (`FR.html`).

### `serve_static(self, path)`

Serves static files based on the provided path (CSS, images).

### `get_recipes(self)`

Fetches all recipes from the database and returns them in JSON format.

### `do_POST(self)`

Handles POST requests:
- **/recipes**: Adds a new recipe to the database.

### `add_recipe(self)`

Adds a new recipe to the database based on the provided title, ingredients, and instructions.

### `do_DELETE(self)`

Handles DELETE requests:
- **/recipes/{id}**: Deletes a recipe with the specified ID from the database.

### `delete_recipe(self, recipe_id)`

Deletes a recipe with the given ID from the database.
