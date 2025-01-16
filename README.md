# Blog Platform API

This is a simple Node.js and Express API for managing blogs. It uses MongoDB as the database.

## Requirements

- Node.js (v14 or above)
- MongoDB (Atlas or local instance)
- Postman (for testing API)
- Git (optional, for version control)

## Installation

1. **Clone the repository**:

   ```bash
   git clone <repository-url>
   cd blog-platform
   ```

2. **Install dependencies**:

   ```bash
   npm install
   ```

3. **Set up MongoDB**:

   - If using MongoDB Atlas:
     1. Create a cluster in [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
     2. Get the connection string from Atlas and replace `<username>`, `<password>`, and `<database>` with your details.
   - If using a local MongoDB instance:
     1. Make sure MongoDB is running on your machine.

4. **Create a `.env` file**:
   In the root of the project, create a file named `.env` and add the following content:

   ```
   MONGO_URI=<Your MongoDB Connection String>
   PORT=5000
   ```

5. **Start the server**:

   ```bash
   node server.js
   ```

6. **Download Postman**:
   Download and install Postman from [Postman Download](https://www.postman.com/downloads/).

## Usage

### Step-by-Step Guide to Testing Endpoints in Postman

1. **Start the server**:

   ```bash
   node server.js
   ```

2. **Open Postman**:

   - Open the Postman application.

3. **Create a new request**:

   - Click the **`+`** button to create a new request.

4. **Test Create (POST)**:

   - Select the method as **POST**.
   - Enter the URL: `http://localhost:5000/api/blogs`.
   - Click **Body**, select **raw**, and set the format to `JSON`.
   - Paste the following JSON:
     ```json
     {
       "title": "My First Blog",
       "content": "This is the content of my first blog post."
     }
     ```
   - Click the **Send** button.

5. **Test Retrieve All (GET)**:

   - Select the method as **GET**.
   - Enter the URL: `http://localhost:5000/api/blogs`.
   - Click the **Send** button.

6. **Test Update (PUT)**:

   - Select the method as **PUT**.
   - Enter the URL: `http://localhost:5000/api/blogs/:id` (replace `:id` with a valid blog ID).
   - Paste the following JSON:
     ```json
     {
       "title": "Updated Blog Title",
       "content": "This is the updated content of the blog.",
       "author": "Updated Author"
     }
     ```
   - Click the **Send** button.

7. **Test Delete (DELETE)**:
   - Select the method as **DELETE**.
   - Enter the URL: `http://localhost:5000/api/blogs/:id` (replace `:id` with a valid blog ID).
   - Click the **Send** button.

## Directory Structure

```
blog-platform/
├── config/
│   └── db.js           # MongoDB connection setup
├── controllers/
│   └── blogController.js # Logic for handling API requests
├── models/
│   └── Blog.js         # Blog schema for MongoDB
├── routes/
│   └── blogRoutes.js   # API routes
├── public/
│   └── index.html      # Placeholder for frontend (if needed)
├── server.js           # Entry point for the application
├── .env                # Environment variables (not included, create your own)
├── package.json        # Project metadata and dependencies
└── README.md           # Project documentation
```

## License

This project is licensed under the MIT License.
