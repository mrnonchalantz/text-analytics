import PyPDF2

**Read the PDF file**
with open('Business_Proposal.pdf', 'rb') as file:
reader = PyPDF2.PdfReader(file)

    **Ensure the document has at least 2 pages**
    if len(reader.pages) >= 2:
        text = reader.pages[1].extract_text()  # Page index starts from 0
    else:
        text = "Error: The document does not have a second page."

**Print the extracted text**
print("Extracted Text from Page 2:\n", text)

**Store the extracted text in a file**
with open('business_proposal_page_2.txt', 'w', encoding='utf-8') as output:
output.write(text)

**Result**
Extracted Text from Page 2:
AUTHORS:  
Amy Baker, Finance Chair, x345, abaker@ourcompany.com  
Chris Donaldson, Accounting Dir., x621, cdonaldson@ourcompany.com  
Erin Freeman, Sr. VP, x879, efreeman@ourcompany.com
