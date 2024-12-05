# Huffman Encoder and Decoder

This project implements the **Huffman Coding** algorithm using **Spring Boot** for both encoding and decoding of text. It provides a backend API for encoding a string into a binary format and decoding it back to its original form. The encoding also includes the frequency map as metadata to facilitate decoding.

## Features
- **Huffman Encoding**: Converts a given string into its encoded binary form using Huffman coding.
- **Huffman Decoding**: Decodes the binary string back to its original form using the frequency map included in the encoded string.
- **Spring Boot Application**: REST API endpoints to handle encoding and decoding requests.

## Prerequisites
- Java 17 or higher
- Maven for dependency management
- Spring Boot for building the backend
- A web browser or API testing tool like Postman for interacting with the API

## Project Structure
```
src/
 └── main/
     ├── java/
     │   └── com/mugiwara/huffmancoder/
     │       ├── controller/              # Contains the controller for handling HTTP requests
     │       ├── service/                 # Contains the logic for Huffman encoding and decoding
     │       ├── dto/                     # Contains data transfer objects (DTOs)
     │       └── HuffmanApplication.java  # Main entry point for Spring Boot application
     ├── resources/
     │   └── application.properties       # Application configuration
```

## API Endpoints

### 1. **POST /huffman/encode**
Encodes a given input string into a binary representation using Huffman coding and returns the encoded string along with the frequency map as metadata.

**Request:**
```bash
POST /huffman/encode?input=abbccda
```

**Response:**
```json
{
  "encodedString": "1010011110011",
  "frequencyMap": "a:2;b:2;c:2;d:1;"
}
```

### 2. **POST /huffman/decode**
Decodes an encoded string using the frequency map to reconstruct the original input string.

**Request:**
```bash
POST /huffman/decode?encodedInput=1010011110011|a:2;b:2;c:2;d:1;
```

**Response:**
```json
{
  "decodedString": "abbccda"
}
```

## Running the Project

### 1. Clone the repository:
```bash
git clone https://github.com/your-username/huffman-coding-springboot.git
cd huffman-coding-springboot
```

### 2. Build the project using Maven:
```bash
mvn clean install
```

### 3. Run the Spring Boot application:
```bash
mvn spring-boot:run
```

The application will start on `http://localhost:8080`.

## Example Usage

### **Encoding Example**
- Request:
  ```bash
  POST http://localhost:8080/huffman/encode?input=abbccda
  ```

- Response:
  ```json
  {
    "encodedString": "1010011110011",
    "frequencyMap": "a:2;b:2;c:2;d:1;"
  }
  ```

### **Decoding Example**
- Request:
  ```bash
  POST http://localhost:8080/huffman/decode?encodedInput=1010011110011|a:2;b:2;c:2;d:1;
  ```

- Response:
  ```json
  {
    "decodedString": "abbccda"
  }
  ```

## Technologies Used
- **Spring Boot**: Framework for building the backend service.
- **Java 17**: Programming language used for the backend.
- **Maven**: Build automation tool for managing dependencies and packaging.
- **Huffman Coding**: Lossless data compression algorithm used for encoding and decoding the data.

## Contributing
Feel free to fork the repository, submit issues, and contribute to this project. If you find any bugs or have suggestions for improvements, open an issue or create a pull request.

## License
This project is open-source and available under the MIT License.
