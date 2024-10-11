# Spring Security - In-Memory Authentication

This project demonstrates the use of **In-Memory Authentication** with Spring Security. In this setup, user credentials (username, password, and roles) are stored in memory for authentication. This approach is ideal for small applications, quick setups, prototyping, or unit testing.

## Application Overview

In-memory authentication is a lightweight, quick-to-implement security method for handling user login and authentication in Spring applications. This approach is useful in scenarios where you don't want to integrate a full database or an external authentication service.

### Key Features:
- **Basic User Authentication**: Credentials are stored directly in memory.
- **Different User Roles**: Roles such as `USER` and `ADMIN` can be assigned to different users.
- **Form-Based Login**: Provides a user interface for login.
- **HTTP Basic Authentication**: Also supports HTTP basic authentication, which is useful for API-based access.

### Use Cases:
- **Testing Purposes**: Quickly test authentication mechanisms without the need for database setup.
- **Small-Scale Applications**: Ideal for personal projects, internal tools, or demos.
- **Quick Prototyping**: Develop fast security solutions when time or resources are limited.

## Benefits of In-Memory Authentication

1. **Simplicity**: No need to configure an external database or connect to a user directory like LDAP. Just define users in your configuration, and you're ready to go.
2. **Quick Setup**: Great for testing, as it avoids time-consuming database integration steps.
3. **No External Dependencies**: Since everything is handled in memory, there is no reliance on external systems like databases, which means faster development iterations.
4. **Easy Role Management**: User roles can be easily defined and managed within the configuration, making it straightforward to implement role-based access control.

## Limitations of In-Memory Authentication

1. **Not Scalable**: It is impractical for large-scale applications that need to manage many users.
2. **No Persistence**: The user information is stored in memory and will be lost when the application is restarted. This makes it unsuitable for real-world, production applications.
3. **Security Risks**: Storing credentials in memory, especially in plain text, is not secure and should only be used for testing or development environments.
4. **Limited Flexibility**: Managing complex user requirements, such as password policies, account locking, or multi-factor authentication, is not feasible with this approach.

## Authentication Flow

The in-memory authentication setup uses Spring Security to manage user authentication. Here’s a breakdown of how the authentication flow works in this project:

1. **User Definition**: Usernames, passwords, and roles are defined in the application's configuration.
2. **Login Methods**:
   - **Form-Based Login**: Provides a login page where users can enter their credentials.
   - **HTTP Basic Authentication**: Allows users to authenticate via HTTP headers, useful for APIs.
3. **Authorization**: The system checks if the authenticated user has the correct role (`USER`, `ADMIN`, etc.) to access specific resources.
4. **Session Management**: Once authenticated, the user session is maintained, allowing continued access to authorized resources.

## Example Users

Two users are configured in this application:

- **user1**:
  - Role: `USER`
  - Username: `user1`
  - Password: `password1`

- **admin**:
  - Role: `ADMIN`
  - Username: `admin`
  - Password: `password1`

These credentials are stored in memory and are not persisted across restarts.
