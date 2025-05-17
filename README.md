# Rust Web Server Implementation

## Reflections

1. Handle-connection, check response
   - Rust's ownership system and type safety make it surprisingly straightforward to build a basic web server
   - The standard library provides all necessary tools (TcpListener, TcpStream) for network programming
   - Single-threaded implementation is simple but has limitations:
     * Can only handle one request at a time
     * Subsequent requests must wait for the current one to complete
     * Not suitable for production use with multiple concurrent users
   - This implementation serves as a great learning exercise for understanding:
     * Basic TCP networking concepts
     * HTTP protocol fundamentals
     * Rust's error handling patterns
     * File I/O operations

<img width="917" alt="image" src="https://github.com/user-attachments/assets/7edcc7a5-677f-43cd-9da9-87eb6620deda" />
<img width="883" alt="image" src="https://github.com/user-attachments/assets/79492ffc-5146-4632-b2eb-236e974aebf8" />

2. Returning HTML
   - Rust's performance characteristics make it an excellent choice for web servers
   - The implementation demonstrates:
     * How to parse HTTP requests using Rust's iterator methods
     * Proper HTTP response formatting with status codes and headers
     * File serving capabilities through the standard library
     * Error handling using Rust's Result type
   - The code shows Rust's ability to handle:
     * Network I/O operations
     * String manipulation for HTTP headers
     * File system operations
     * Memory safety without garbage collection

3. Validating request and selectively responding
   - The implementation demonstrates selective response handling:
     * Parses the first line of HTTP request to check request type and path
     * Returns different HTML pages based on the request path
     * Uses pattern matching with if/else to determine appropriate response
     * Maintains proper HTTP response formatting regardless of path
   - Key learning points:
     * HTTP request validation and routing
     * Conditional response logic
     * Serving multiple HTML files
     * Error handling for invalid requests
   - The code shows how to:
     * Extract and validate request information
     * Make routing decisions
     * Return appropriate status codes
     * Serve different content based on request