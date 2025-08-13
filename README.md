# Paper16: Binary to Text and Back

Paper16 is a simple suite of web tools that allows you to convert any file into a text string and decode that text string back into the original file. This is useful for archiving data on paper, transmitting data over text-only channels, or creating human-readable backups of binary files.

***

## How It Works

The core concept behind Paper16 is a hexadecimal (base-16) encoding scheme.

* **Encoding:** Every byte (8 bits) of a file is split into two 4-bit "nibbles." Each nibble is then represented by a single hexadecimal character (0-9, A-F). This turns any binary data into a text string where every two characters represent one byte of the original file.
* **Decoding:** The decoder reverses this process. It takes the hexadecimal text string, breaks it into pairs of characters, and converts each pair back into a single byte. It then assembles these bytes to reconstruct the original file.

***

## Tools

The repository contains three main HTML files, each with embedded JavaScript. All tools are self-contained and require no server to run.

### 1. `encoder.html`
This tool takes any file as input, reads its binary data, and outputs a continuous string of hexadecimal characters.

**Key features:**
* Reads any file type.
* Outputs a single, compact text string.

### 2. `decoder.html`
This tool takes a hexadecimal text string as input, decodes it, and provides a download link for the reconstructed file.

**Key features:**
* Validates input for correct hex characters and even length.
* Reconstructs the original file as a downloadable Blob.

### 3. `decoder-ocr.html`
This advanced decoder uses **Tesseract.js** to perform Optical Character Recognition (OCR) on an image file. It extracts any hexadecimal text from the image, automatically populates the text area, and then decodes the data. This is ideal for scanning text from a physical document. 

**Key features:**
* Integrates **Tesseract.js** via CDN.
* Takes an image file as input.
* Automates the extraction of text before decoding.

***

## Usage

Simply download or clone this repository and open any of the `.html` files in your web browser.

* To **encode** a file, open `encoder.html` and select a file. 
https://demensdeum.com/software/paper16/encoder.html

* To **decode** a text string, open `decoder.html` and paste your text. 
https://demensdeum.com/software/paper16/decoder.html

* To **decode** from an image, open `decoderOCR.html` and select your image file. 
https://demensdeum.com/software/paper16/decoderOCR.html
