##README

This is a README file that provides an overview and basic documentation for the codebase. It includes information about the project structure, database models, routes, and setup instructions.
Project Structure
The project has the following structure:

- app.py
- config.py
- models.py
- routes.py
- migrations/
  
  • app.py - This is the main Flask application file that initializes the Flask app, configures the database connection, sets up migrations, and registers routes.
  
  • config.py - This file contains configuration settings for the Flask app, including the database URI and JWT secret key.
  
  • models.py - This file defines the SQLAlchemy models for the application, including the User, Task, and Category models.
  
  • routes.py - This file contains the route definitions for the API endpoints, such as user signup, login, task management, and category operations.
  
  • migrations/ - This directory contains database migration scripts generated by Flask-Migrate.

#Database Models

The application uses SQLAlchemy to define and interact with the database. Here are the main database models defined in models.py:
    • User - Represents a user in the system. It has attributes such as id, username, email, and password.
    • Task - Represents a task that belongs to a user. It has attributes such as id, title, description, due_date, created_at, updated_at, status, and user_id.
    • Category - Represents a category that can be assigned to tasks. It has attributes such as id and name.
The models are defined using SQLAlchemy's declarative syntax, and relationships between the models are established using foreign keys and relationship fields.

#Routes

The application provides the following API routes:
    • POST /api/users/signup - Allows users to sign up by providing a username, email, and password.
    • POST /api/users/login - Allows users to log in with their username and password, returning a JWT token upon successful authentication.
    • GET /api/tasks - Retrieves all tasks associated with the authenticated user.
    • POST /api/tasks - Creates a new task for the authenticated user.
    • GET/PUT/DELETE /api/tasks/<task_id> - Retrieves, updates, or deletes a specific task identified by task_id.
    • PATCH /api/tasks/<task_id>/complete - Marks a task as complete.
    • PATCH /api/tasks/<task_id>/incomplete - Marks a task as incomplete.
    • POST /api/tasks/<task_id>/assign - Assigns a task to another user.
    • GET /api/categories - Retrieves all categories.
    • POST /api/categories - Creates a new category.
The routes are implemented in routes.py using Flask's route decorators and utilize the database models and functions defined in models.py for data manipulation.

#Setup Instructions

To set up and run the application, follow these steps:
    1. Clone the repository to your local machine.
    2. Install the required dependencies by running pip install -r requirements.txt.
    3. Set up a PostgreSQL database and update the SQLALCHEMY_DATABASE_URI in app.py with your database connection details.
    4. Set a JWT secret key in the JWT_SECRET_KEY field in config.py.
    5. Apply the database migrations by running flask db upgrade in the project directory.
    6. Start the Flask development server by running flask run.
    7. The API will be accessible at http://localhost:5000/api.
    
Make sure to adjust the database connection details and other configurations according to your specific environment.
You now have the application up and running, and you can start making API requests to manage users, tasks, and categories.
Note: This README assumes that you have Python, Flask, and PostgreSQL installed and properly configured on your system.
