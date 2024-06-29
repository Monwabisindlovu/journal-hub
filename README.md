# JournalHub

JournalHub is a Node.js and MongoDB application for creating, reading, updating, and deleting journal entries.

## Features

- User registration and authentication using JWT
- Create, read, update, and delete journal entries
- Store data in MongoDB
- Redis integration for caching
- React frontend (in progress)

## Prerequisites

- Node.js (version 16)
- MongoDB
- Redis

## Installation

1. Clone the repository:

    ```sh
    git clone https://github.com/your-username/JournalHub.git
    cd JournalHub
    ```

2. Install dependencies:

    ```sh
    npm install
    ```

3. Create a `.env` file in the root directory and add the following variables:

    ```env
    MONGO_URI=mongodb://localhost:27017/journalhub
    JWT_SECRET=your_jwt_secret
    REDIS_URL=redis://localhost:6379
    ```

4. Start MongoDB and Redis services.

5. Start the server:

    ```sh
    npm run start-server
    ```

6. If you want to work on the React frontend, navigate to the `client` directory and install dependencies:

    ```sh
    cd client
    npm install
    ```

7. Start the React development server:

    ```sh
    npm start
    ```

## Usage

1. Register a new user:

    ```sh
    curl -X POST http://localhost:5000/register -H "Content-Type: application/json" -d '{
        "name": "John Doe",
        "email": "johndoe@example.com",
        "password": "password123"
    }'
    ```

2. Log in with the registered user to get a JWT token:

    ```sh
    curl -X POST http://localhost:5000/login -H "Content-Type: application/json" -d '{
        "email": "johndoe@example.com",
        "password": "password123"
    }'
    ```

3. Use the JWT token to create a journal entry:

    ```sh
    curl -X POST http://localhost:5000/journalEntries -H "Authorization: Bearer <your_jwt_token>" -H "Content-Type: application/json" -d '{
        "date": "2024-06-27T00:00:00Z",
        "title": "My Journal Entry",
        "content": "This is the content of my journal entry."
    }'
    ```

4. Fetch all journal entries for a user:

    ```sh
    curl -X GET http://localhost:5000/journalEntries/user/<user_id> -H "Authorization: Bearer <your_jwt_token>"
    ```

## Contributing

1. Fork the repository
2. Create a new branch (`git checkout -b feature-branch`)
3. Make your changes
4. Commit your changes (`git commit -m 'Add some feature'`)
5. Push to the branch (`git push origin feature-branch`)
6. Create a pull request

## License

This project is licensed under the MIT License.

