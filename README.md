# Huffman Coding Spring Boot Integration

This project integrates the Huffman Coding algorithm into a Spring Boot application. It provides both a backend for encoding and decoding text, and a frontend interface for users to interact with.

## Project Overview
The application implements the Huffman Coding algorithm for text compression and decompression. It provides a simple REST API for encoding and decoding text, as well as a frontend for easy interaction.

## Features
- **Text Encoding**: Compresses text into binary based on character frequencies using the Huffman Coding algorithm.
- **Text Decoding**: Decodes the binary string back into the original text.
- **REST API**: Exposes endpoints to encode and decode text.
- **Frontend Interface**: A simple HTML page to interact with the API.

## Installation

### Prerequisites
- Java 21 or higher
- Maven or Gradle for building the Spring Boot project
- Spring Boot 2.5 or later
- Web browser for accessing the frontend

### Steps to Run Locally

1. **Clone the repository**:
   ```bash
   git clone https://github.com/MatheshRavichandrann/HuffmanCodingSpringBoot.git
   ```

2. **Navigate to the project directory**:
   ```bash
   cd HuffmanCodingSpringBoot
   ```

3. **Build and run the Spring Boot project**:
   ```bash
   mvn spring-boot:run
   ```

   This will start the Spring Boot server on `http://localhost:8080`.

4. **Open `index.html` in a browser**:
   Navigate to the `src/main/resources/static` folder and open `index.html` in your preferred browser.

## API Endpoints

### Encode Text
- **URL**: `/api/huffman/encode`
- **Method**: `POST`
- **Parameters**: `input` (The text to encode)
- **Response**: Encoded binary string

### Decode Text
- **URL**: `/api/huffman/decode`
- **Method**: `POST`
- **Parameters**: 
  - `input`: The original text for tree building
  - `encodedText`: The binary string to decode
- **Response**: Decoded original text

## Frontend (HTML + JavaScript)

The frontend allows the user to input text for encoding or decoding. The JavaScript code interacts with the Spring Boot backend via REST API calls.

## Usage

- **Encoding**: Enter your text in the provided text box and click the "Encode" button to get the encoded binary string.
- **Decoding**: Enter the encoded binary string and click the "Decode" button to retrieve the original text.

## Contributing
Feel free to fork the repository and submit pull requests. Contributions are welcome!

## License
This project is licensed under the MIT License - see the LICENSE file for details.
