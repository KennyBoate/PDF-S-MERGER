# PDF-S-MERGER:

import PyPDF2

def merge_pdfs(output_filename, *pdf_files):
    # Create a PDF writer object to write the merged PDF
    pdf_writer = PyPDF2.PdfWriter()

    # Iterate through each PDF file
    for pdf_file in pdf_files:
        # Open each PDF file in binary mode
        with open(pdf_file, 'rb') as pdf:
            # Create a PDF reader object
            pdf_reader = PyPDF2.PdfReader(pdf)
            
            # Add all pages from the current PDF to the writer
            for page_num in range(pdf_reader.numPages):
                pdf_writer.addPage(pdf_reader.getPage(page_num))

    # Write the merged PDF to the output file
    with open(output_filename, 'wb') as output_pdf:
        pdf_writer.write(output_pdf)

if __name__ == "__main__":
    # Provide the output filename and input PDF filenames as arguments
    output_filename = "merged.pdf"
    input_pdfs = ["file1.pdf", "file2.pdf", "file3.pdf"]

    merge_pdfs(output_filename, *input_pdfs)

    print(f"Merged PDF saved as {output_filename}")























simple Python program that merges two or more PDF files into one:
Import the PyPDF2 library:

python
Copy code
import PyPDF2
This line imports the PyPDF2 library, which provides functionalities to work with PDF files.

Define the merge_pdfs function:

python
Copy code
def merge_pdfs(output_filename, *pdf_files):
This function takes an output_filename (the name of the merged PDF file) and a variable number of pdf_files as input.

Create a PDF writer object:

python
Copy code
pdf_writer = PyPDF2.PdfWriter()
This line creates a PDF writer object, which will be used to write the merged PDF.

Iterate through each input PDF file:

python
Copy code
for pdf_file in pdf_files:
It loops through each input PDF file specified in the pdf_files argument.

Open each PDF file in binary mode:

python
Copy code
with open(pdf_file, 'rb') as pdf:
It opens each PDF file in binary mode ('rb').

Create a PDF reader object:

python
Copy code
pdf_reader = PyPDF2.PdfReader(pdf)
This line creates a PDF reader object for the current PDF file.

Add all pages from the current PDF to the writer:

python
Copy code
for page_num in range(pdf_reader.numPages):
    pdf_writer.addPage(pdf_reader.getPage(page_num))
It iterates through all pages in the current PDF file and adds them to the PDF writer.

Write the merged PDF to the output file:

python
Copy code
with open(output_filename, 'wb') as output_pdf:
    pdf_writer.write(output_pdf)
Finally, it writes the merged PDF to the specified output_filename in binary mode ('wb').

Run the script if executed directly:

python
Copy code
if __name__ == "__main__":
    # Provide the output filename and input PDF filenames as arguments
    output_filename = "merged.pdf"
    input_pdfs = ["file1.pdf", "file2.pdf", "file3.pdf"]

    merge_pdfs(output_filename, *input_pdfs)

    print(f"Merged PDF saved as {output_filename}")
If the script is executed directly (not imported as a module), it merges the specified input PDF files and prints a message indicating where the merged PDF is saved.

That's the basic breakdown of the code. It essentially reads each input PDF, extracts its pages, and appends them to a new PDF file, resulting in a merged PDF file.





