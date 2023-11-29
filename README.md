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
#pip install PyPDF2
 # Create a PDF writer object to write the merged PDF
  # Iterate through each PDF file
   # Open each PDF file in binary mode
   # Create a PDF reader object
    # Add all pages from the current PDF to the writer
    # Write the merged PDF to the output file
     # Provide the output filename and input PDF filenames as arguments

     
#Replace "file1.pdf", "file2.pdf", etc., with the actual file names you want to merge. 
# The merged PDF will be saved with the name specified in the output_filename variable.
#Save this code in a Python file (e.g., merge_pdfs.py) and run it using:
