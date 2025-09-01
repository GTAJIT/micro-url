# Micro-URL 🔗

![GitHub repo size](https://img.shields.io/github/repo-size/codesbyjit/micro-url?style=for-the-badge)
![GitHub language count](https://img.shields.io/github/languages/count/codesbyjit/micro-url?style=for-the-badge)
![GitHub last commit](https://img.shields.io/github/last-commit/codesbyjit/micro-url?style=for-the-badge)

A lightweight and high-performance URL shortening service built to be fast, scalable, and easy to deploy.

---

### ## Description

**Micro-URL** is a backend service that transforms long URLs into short, easy-to-share links. When a user visits the shortened link, they are seamlessly redirected to the original long URL. This project is ideal for applications requiring link tracking, branded short domains, or simply a cleaner way to share links across platforms.

### ## Key Features

-   **Create Short URLs:** Generate a unique, short alias for any long URL via a simple API endpoint.
-   **Fast Redirects:** Near-instantaneous redirection from the short URL to the original destination.
-   **Scalable Architecture:** Designed to handle a high volume of requests with minimal latency.
-   **Easy Deployment:** Containerized with Docker for consistent and hassle-free setup.
-   **(Optional) Custom Aliases:** Support for user-defined custom short links.
-   **(Optional) Link Analytics:** Track clicks and gather basic analytics for each link.

---

### ## Technology Stack

This project is built with a modern and efficient stack:

-   **Backend:** Go (Golang)
-   **Database:** Redis (for caching/storage of URL mappings)
-   **Deployment:** Docker / Docker Compose

---

### ## Getting Started

Follow these instructions to get a local copy up and running for development and testing.

#### ### Prerequisites

-   [Docker](https://www.docker.com/get-started) and [Docker Compose](https://docs.docker.com/compose/install/) must be installed on your machine.

#### ### Installation & Running Locally

1.  **Clone the repository:**
    ```sh
    git clone [https://github.com/codesbyjit/micro-url.git](https://github.com/codesbyjit/micro-url.git)
    cd micro-url
    ```

2.  **Environment Variables:**
    Create a `.env` file in the root of the project and add the necessary environment variables. Start by copying the example file:
    ```sh
    cp .env.example .env
    ```
    Now, modify the `.env` file with your desired settings (e.g., server port, database credentials).

3.  **Run with Docker Compose:**
    This single command will build the Go application, start the Redis container, and run the service.
    ```sh
    docker-compose up --build
    ```

The service should now be running on the port you specified in your `.env` file (e.g., `http://localhost:8080`).

---

### ## API Usage

The API is simple and straightforward.

#### ### 1. Create a Short URL

-   **Endpoint:** `POST /`
-   **Content-Type:** `application/json`

-   **Request Body:**
    ```json
    {
      "url": "[https://www.google.com/search?q=very-long-url-that-needs-to-be-shortened](https://www.google.com/search?q=very-long-url-that-needs-to-be-shortened)"
    }
    ```

-   **Success Response (200 OK):**
    ```json
    {
      "short_url": "http://localhost:8080/aB1cD2eF"
    }
    ```

#### ### 2. Redirect to Original URL

-   **Endpoint:** `GET /{shortCode}`

-   **Description:**
    Simply navigate to the `short_url` returned from the creation endpoint in your browser or any HTTP client.

-   **Example:**
    Visiting `http://localhost:8080/aB1cD2eF` will redirect you to `https://www.google.com/search?q=very-long-url-that-needs-to-be-shortened`.

---

### ## Contributing

Contributions are welcome! If you have suggestions for how this project could be improved, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

### ## License

Distributed under the MIT License. See `LICENSE` file for more information.
