## Huffman Encoder and Decoder with Spring Boot

This project implements Huffman Coding for text compression and decompression using Spring Boot. It provides a REST API for both encoding and decoding operations.

### Features

* **Huffman Encoding:** Converts a string into its compressed binary form using Huffman coding.
* **Huffman Decoding:** Recovers the original string from the encoded binary data with the help of a frequency map.
* **Spring Boot Application:** Offers REST API endpoints to handle encoding and decoding requests.

### Prerequisites

* Java 17 or later
* Maven for dependency management
* Spring Boot for building the backend
* Web browser or API testing tool (Postman) for interacting with the API

### Project Structure

```
src/
  main/
    java/
      com/mugiwara/huffmancoder/
        controller/              # Contains the controller for handling HTTP requests
        service/                 # Contains the logic for Huffman encoding and decoding
        dto/                     # Contains data transfer objects (DTOs)
        HuffmanApplication.java  # Main entry point for Spring Boot application
    resources/
      application.properties       # Application configuration
```

### API Endpoints

1. **POST /huffman/encode**

   Encodes an input string using Huffman coding and returns the encoded binary representation along with a frequency map stored as metadata.

   **Request:**

   ```
   POST /huffman/encode?input=abbccda
   ```

   **Response:**

   ```json
   {
     "encodedString": "1010011110011",
     "frequencyMap": "a:2;b:2;c:2;d:1;"
   }
   ```

2. **POST /huffman/decode**

   Decodes an encoded string using the provided frequency map to reconstruct the original string.

   **Request:**

   ```
   POST /huffman/decode?encodedInput=1010011110011|a:2;b:2;c:2;d:1;
   ```

   **Response:**

   ```json
   {
     "decodedString": "abbccda"
   }
   ```

### Running the Project

1. Clone the repository (replace with your actual repository URL):

   ```
   git clone https://github.com/your-username/huffman-coding-springboot.git
   cd huffman-coding-springboot
   ```

2. Build the project using Maven:

   ```
   mvn clean install
   ```

3. Run the Spring Boot application:

   ```
   mvn spring-boot:run
   ```

   The application will start on `http://localhost:8080`.

### Example Usage

**Encoding Example**

**Request:**

```
POST http://localhost:8080/huffman/encode?input=abbccda
```

**Response:**

```json
{
  "encodedString": "1010011110011",
  "frequencyMap": "a:2;b:2;c:2;d:1;"
}
```

**Decoding Example**

**Request:**

```
POST http://localhost:8080/huffman/decode?encodedInput=1010011110011|a:2;b:2;c:2;d:1;
```

**Response:**

```json
{
  "decodedString": "abbccda"
}
```

### Technologies Used

* Spring Boot: Framework for building the backend service.
* Java 17: Programming language for the backend development.
* Maven: Build automation tool for dependency management and packaging.
* Huffman Coding: Lossless data compression algorithm for encoding and decoding the data.

### Contributing

Feel free to contribute to this project by forking the repository, submitting issues, and creating pull requests.

### License

This project is open-source and available under the MIT License.
