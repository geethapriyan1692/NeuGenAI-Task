## ENGINEERING CHATPOT
This project is a chatbot designed to analyze engineering drawings in PDF format. The chatbot can extract images from the PDF, perform OCR (Optical Character Recognition) to detect text (including mathematical expressions), and generate answers based on the content of the images. Users can ask questions about the engineering drawings, and the chatbot will find the most relevant image, extract calculations, and provide an answer.

## Features:
Extract images from engineering drawing PDFs.
Use CLIP model to find the most relevant images based on text queries.
Perform OCR on images to extract mathematical expressions.
Evaluate mathematical expressions and return results.
Provide relevant responses using the RAG (Retrieval Augmented Generation) model.

## Requirements:
Before running this project, make sure you have the following dependencies installed:

Python Libraries:
torch
transformers
gradio
numpy
faiss-cpu
Pillow
fitz (PyMuPDF)
sympy
pytesseract
opencv-python


## Setup:
1. Extracting Images from PDF:
The chatbot first extracts images from the PDF files containing the engineering drawings. The fitz (PyMuPDF) library is used to extract images from each page in the PDF.

2. Embedding Images Using CLIP:
The extracted images are then passed through a CLIP (Contrastive Language-Image Pretraining) model to generate image embeddings. These embeddings help in retrieving the most relevant image based on the user’s query.

3. Build FAISS Index:
FAISS (Facebook AI Similarity Search) is used to build an index for fast retrieval of the most relevant image embeddings. This allows the chatbot to efficiently find the closest image match for a user's query.

4. Processing OCR and Mathematical Expressions:
After identifying the most relevant image, the chatbot performs OCR using Tesseract to extract any text, particularly mathematical expressions, from the image. The expressions are then parsed and evaluated using the sympy library.

5. Generate Response:
The chatbot uses a RAG (Retrieval-Augmented Generation) model to generate a natural language response, incorporating the extracted mathematical results or context from the image.

6. Gradio Interface:
The chatbot is wrapped in a Gradio interface, allowing users to input text queries and receive answers in a user-friendly web interface.

## Running the Application:
1.Clone the repository or copy the code to your local machine.

2.Ensure you have all dependencies installed (as outlined above).

3.Place the PDF file containing the engineering drawings in the project directory.

4.Run the Python script

5.This will start the Gradio interface and open a local web server (typically on http://localhost:7860).

In the web interface, you can input questions like:

"What is the value in the table on page 2?"
"Solve the equation in the image from page 5."

The chatbot will search for the most relevant image, extract mathematical expressions, and provide an answer.

## Troubleshooting:
Tesseract Not Found: Make sure Tesseract is properly installed and added to your system’s PATH.
Library Installation Issues: If you encounter issues with libraries, try installing them in a virtual environment.

## Contributing:
Feel free to fork the repository and submit pull requests if you'd like to contribute to the development of this chatbot!
