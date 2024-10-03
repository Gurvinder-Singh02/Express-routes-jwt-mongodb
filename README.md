# Backend API for Course Management System

This is a backend application for managing users, courses, and purchases. It is built with Node.js, Express, and MongoDB.

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Set up your environment variables:
   - Create a `.env` file in the root directory and add your MongoDB URL:
     ```
     MONGO_URL=mongodb://localhost:27017/your_database_name
     JWT_USER_PASSWORD=your_jwt_secret
     JWT_ADMIN_PASSWORD=your_admin_jwt_secret
     ```

4. Start the server:
   ```bash
   npm start
   ```

The server will be running on `http://localhost:3000`.

## API Endpoints

### User Endpoints

#### Signup
- **POST** `/api/v1/user/signup`
- **Request Body**:
    ```json
    {
        "email": "user@example.com",
        "password": "password123",
        "firstName": "John",
        "lastName": "Doe"
    }
    ```

#### Signin
- **POST** `/api/v1/user/signin`
- **Request Body**:
    ```json
    {
        "email": "user@example.com",
        "password": "password123"
    }
    ```
- **Response**:
    ```json
    {
        "token": "your_jwt_token"
    }
    ```

#### Get Purchases
- **GET** `/api/v1/user/purchases`
- **Headers**:
    ```
    Authorization: Bearer your_jwt_token
    ```

### Admin Endpoints

#### Admin Signup
- **POST** `/api/v1/admin/signup`
- **Request Body**:
    ```json
    {
        "email": "admin@example.com",
        "password": "adminpassword123",
        "firstName": "Jane",
        "lastName": "Doe"
    }
    ```

#### Admin Signin
- **POST** `/api/v1/admin/signin`
- **Request Body**:
    ```json
    {
        "email": "admin@example.com",
        "password": "adminpassword123"
    }
    ```

#### Create Course
- **POST** `/api/v1/admin/course`
- **Request Body**:
    ```json
    {
        "title": "Web Development Bootcamp",
        "description": "Learn web development from scratch.",
        "imageUrl": "http://example.com/image.jpg",
        "price": 199.99
    }
    ```
- **Headers**:
    ```
    Authorization: Bearer your_admin_jwt_token
    ```

### Course Endpoints

#### Purchase Course
- **POST** `/api/v1/course/purchase`
- **Request Body**:
    ```json
    {
        "courseId": "course_id_here"
    }
    ```
- **Headers**:
    ```
    Authorization: Bearer your_jwt_token
    ```

#### Preview Courses
- **GET** `/api/v1/course/preview`

## Fake Data Examples

Here are some example requests using fake data:

1. **User Signup**:
    ```json
    {
        "email": "jane.doe@example.com",
        "password": "mypassword",
        "firstName": "Jane",
        "lastName": "Doe"
    }
    ```

2. **User Signin**:
    ```json
    {
        "email": "jane.doe@example.com",
        "password": "mypassword"
    }
    ```

3. **Admin Signup**:
    ```json
    {
        "email": "admin@example.com",
        "password": "adminpass",
        "firstName": "Admin",
        "lastName": "User"
    }
    ```

4. **Create Course**:
    ```json
    {
        "title": "Introduction to Node.js",
        "description": "Learn the basics of Node.js.",
        "imageUrl": "http://example.com/nodejs-course.jpg",
        "price": 49.99
    }
    ```

## Dependencies

- express: ^4.x
- mongoose: ^6.x
- jsonwebtoken: ^8.x
- dotenv: ^8.x
- (Include any other dependencies here)

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
```

### Notes:
- Make sure to replace placeholder URLs and tokens with appropriate values based on your application setup.
- Feel free to modify the structure, styling, and content of this `README.md` to better fit your application's specific features and usage instructions.
