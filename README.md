# Webserv

A lightweight HTTP server implementation in C++, inspired by NGINX, capable of handling multiple requests and supporting CGI execution.

## 🚀 Features

- HTTP/1.1 support
- GET, POST, DELETE methods
- CGI script execution
- Custom error pages
- Configurable server settings
- Autoindex generation
- Chunked transfer encoding
- Persistent connections (Keep-Alive)

## 🛠 Tech Stack

- C++ language
- Socket programming
- Multithreading for handling multiple clients
- File parsing for server configuration
- CGI script support (Python, PHP, etc.)

## 📦 Project Structure

```
Webserv/
├── srcs/            # Source files
├── include/         # Header files
├── Page/            # Static HTML pages and error pages
├── cgi/             # CGI scripts
└── Makefile         # Build configuration
```

## 🚦 Getting Started

### Prerequisites
- macOS or Linux system
- GCC or Clang compiler
- Make utility

### Installation

1. Clone the repository
```bash
git clone <repository-url>
cd Webserv
```

2. Compile the project
```bash
make
```

3. Run the server with a configuration file
```bash
./webserv config/webserv.conf
```

## 🎮 Features Overview

- **GET**: Retrieve static files or dynamically generated content.
- **POST**: Submit data to the server, including file uploads.
- **DELETE**: Remove files from the server.
- **CGI**: Execute scripts like Python or PHP to generate dynamic responses.
- **Autoindex**: Automatically generate directory listings when no index file is present.
- **Custom Error Pages**: Serve user-defined error pages for HTTP status codes.

## 🗒️ Configuration File Format

Example configuration file (`webserv.conf`):
```
server {
    listen 8080;
    server_name localhost;

    root /var/www/html;
    index index.html;

    error_page 404 /Page/error/404.html;

    location /cgi-bin/ {
        cgi_pass /usr/bin/python3;
        root /var/www/cgi-bin;
    }

    location /uploads/ {
        methods POST;
        root /var/www/uploads;
    }
}
```

## 📝 License

This project is part of the 42 school curriculum.
